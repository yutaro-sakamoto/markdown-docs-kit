FROM ubuntu:24.04

RUN apt-get update -y
RUN apt-get install -y git curl build-essential
RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
ENV PATH="/root/.cargo/bin:${PATH}"
RUN cargo install mdbook