## Dockerfile for a haskell environment
FROM nixos/nix

# Use Cachix to avoid compilation
RUN nix-env -iA cachix -f https://cachix.org/api/v1/install 2>&1
RUN cachix use hercules-ci

# Install ghcide
RUN nix-env -iA ghcide-ghc865 -f https://github.com/hercules-ci/ghcide-nix/tarball/master

# install cabal
RUN nix-env --install curl
RUN nix-env --install cabal2nix
RUN nix-env --install nix-prefetch-git
RUN nix-env --install cabal-install

# Set the default shell to bash
ENV SHELL /bin/bash