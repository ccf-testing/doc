# Prerequisites

This page describes how to install the prerequisites required to build the project on Ubuntu (20.04 LTS) and Arch Linux.

## Ubuntu (20.04 LTS)

The packages given here were tested under Ubuntu 20.04 LTS, but could also work on later versions of Ubuntu, possibly requiring adjustments.

Install the following required packages:

```console
# apt install git pipenv cmake ccache rsync ninja-build libgmp-dev autoconf
```

### Python 3.10

Building the project requires Python 3.10, which is (at the time of writing) not available in the official Ubuntu 20.04 package repositories.
Since multiple ways to acquire this Python version exist (e.g., using a user-provided ppa, installing from source or using a tool such as Pyenv), we leave this part to the user, and assume Python 3.10 to be installed in the rest of this guide.

### Rustup

[Rustup](https://rustup.rs/), a toolchain manager for the Rust programming language, is also required to build the project, but not available in the Ubuntu 20.04 repositories.

The official installation instructions for rustup can be found under [https://rustup.rs/](https://rustup.rs/).
We will assume rustup to be installed in the rest of this guide.

## Arch Linux

The following packages are required to build the project:

```console
# pacman -S git openssh python python-pipenv base-devel cmake ninja ccache rsync rustup
```
