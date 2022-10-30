FROM ubuntu:focal

RUN apt-get update -y \
     && apt-get install -y git sudo jq bc make automake wget \
     && apt-get install -y build-essential curl \
     && apt-get install -y libffi-dev libffi7 libgmp-dev libgmp10 \
     && apt-get install -y libncurses-dev libncurses5 libtinfo5 libnuma-dev \
     && apt-get clean

ENV BOOTSTRAP_HASKELL_NONINTERACTIVE=1
ENV GHCUP_INSTALL_BASE_PREFIX=/home/vscode
ENV PATH=${PATH}:/home/vscode/.ghcup/bin

RUN bash -c "curl --proto '=https' --tlsv1.2 -sSf https://get-ghcup.haskell.org | sh"

RUN bash -c "ghcup upgrade"
RUN ghcup install stack
RUN ghcup install hls
RUN cabal update