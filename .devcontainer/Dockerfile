FROM ubuntu:24.04

RUN apt-get update -y
RUN apt-get install -y git curl build-essential
RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
RUN $HOME/.cargo/bin/cargo install mdbook