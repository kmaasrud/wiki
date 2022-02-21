---
title: My experience with Nix
tags: [nix, blog]
---

I've read a lot about [Nix](https://nixos.org) and I've even tested it a couple of times, but it was not until yesterday that I was convinced. I did a voicecall with my friend [@ratsclub](https://freire.dev.br) and he was showing me these really neat tricks on how I can use Nix and Nix Flakes to define my own reproducible development shell for each project I'm doing - I was blown away. Further research into Nix has shown me just how powerful this tool and language can be. 

In this blog post, I will document my firsthand experience with setting up Nix on my system and moving my environment over to it.

# Installing Nix

I use a Macbook Air M1, and on my first try installing Nix - which was a while ago - I quickly discovered that MacOS made this a hastle. After Catalina, you could not write to the root directory, which meant getting the `/nix` directory up and running was a struggle. Luckily, there are workarounds and these are now intergrated into the installer, which made the install very simple. A simple

```
sh <(curl -L https://nixos.org/nix/install)
```

did the trick for me! A reboot was needed, but then everything was up and running smoothly.

# Setting up nix-darwin

I want to manage my system entirely with Nix flakes, so with the guide from [here](https://github.com/LnL7/nix-darwin#flakes-experimental) as a template, I started with the following file:

```nix
{
  description = "kmaasrud's system";

  inputs = {
    nixpkgs.url = "github:nixos/nixpkgs/nixpkgs-21.11-darwin";
    nixpkgs-unstable.url = "github:NixOS/nixpkgs/nixpkgs-unstable";
    darwin.url = "github:lnl7/nix-darwin/master";
    darwin.inputs.nixpkgs.follows = "nixpkgs-unstable";
  };

  outputs = { self, darwin, nixpkgs }: {
    darwinConfigurations = rec {
      mba = darwin.lib.darwinSystem {
        system = "aarch64-darwin";
        modules = [ ./configuration.nix ];
      };
    }
  };
}
```

I put some simple system configuration in `configuration.nix`, built the flake with 

```
nix build .#darwinConfigurations.mba.system
```

and was joyful to see everything working. This gave me the binary `./result/sw/bin/darwin-rebuild` which I could use to bootstrap the system from the same flake. To my dismay, I was met with an error that said I was missing the `/run` directory. The error helpfully said that I needed to include the line `run\tprivate/var/run` in `/etc/synthetic.conf`, which would create the [firmlink](https://derflounder.wordpress.com/2020/01/18/creating-root-level-directories-and-symbolic-links-on-macos-catalina/) I needed. However, it did not tell me I needed to reboot[^1]... This cost me hours of googling to actually discover.

But alas, I did another reboot and tried `./result/sw/bin/darwin-rebuild switch --flake .` again. This time the bootstrap ran without issue. A third reboot was needed, before I continued my journey.

[^1]: I probably should've understood this, but you know how one gets when you are eager to set things up.

# Next step
