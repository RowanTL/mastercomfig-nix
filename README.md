# Overview

A home-manager module to declaratively manage [mastercomfig](https://github.com/mastercomfig/mastercomfig).

# Usage

At the top of `flake.nix` in your inputs:

```nix
inputs = {
  nixpkgs.url = "github:nixos/nixpkgs?ref=nixos-unstable";
  home-manager = {
      url = "github:nix-community/home-manager";
      inputs.nixpkgs.follows = "nixpkgs";
    };
  mastercomfig = {
    url = "github:RowanTL/mastercomfig-nix";
    flake = false;
  };
};
```

Place `imports = [ "${mastercomfig}/mastercomfig.nix" ];` somewhere under your `home-manager.users.<username>`,
and you're ready to configure.

A basic example example is:

```nix
programs.mastercomfig = {
  enable = true;
  preset = "low";
  addons = [ "no-pyroland" "null-canceling-movement" ];
};
```

## Options

Todo
