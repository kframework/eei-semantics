KEEI: K Semantics of the Ethereum Environment Interface ([EEI])
===============================================================

In this repository we provide a model of the Ethereum Environment Interface in K.
This model was originally obtained by splitting out the blockchain-specific parts of [KEVM].

Installing/Building
-------------------

### System Dependencies

The following are needed for building/running KEVM:

-   [git]
-   [Pandoc >= 1.17] is used to generate the `*.k` files from the `*.md` files.
-   GNU [Bison], [Flex], and [Autoconf].
-   GNU [libmpfr] and [libtool].
-   Java 8 JDK (eg. [OpenJDK])
-   [Opam], **important**: Ubuntu users prior to 15.04 **must** build from source, as the Ubuntu install for 14.10 and prior is broken.
    `opam repository` also requires `rsync`.

On Ubuntu >= 15.04 (for example):

```sh
sudo apt-get install make gcc maven openjdk-8-jdk flex opam pkg-config libmpfr-dev autoconf libtool pandoc zlib1g-dev
```

To run proofs, you will also need [Z3] prover; on Ubuntu:

```sh
sudo apt-get install z3 libz3-dev
```

On ArchLinux:

```sh
sudo pacman -S  base-devel rsync opam pandoc jre8-openjdk mpfr maven z3
```

On OSX, using [Homebrew], after installing the command line tools package:

```sh
brew tap caskroom/cask caskroom/version
brew cask install java8
brew install automake libtool gmp mpfr pkg-config pandoc maven opam z3
```

NOTE: a previous version of these instructions required the user to run `brew link flex --force`. After fetching this
revision, you should first run `brew unlink flex`, as it is no longer necessary and will cause an error if you have the
homebrew version of flex installed instead of the xcode command line tools version.

### Building

After installing the above dependencies, the following command will build submodule dependencies and then KEVM:

```sh
make deps
make build
```

This Repository
---------------

### Layout

The file [eei] contains the semantics of the EEI.

Resources
=========

-   [EEI]: On paper specification of the EEI and ewasm.
-   [EVM Yellowpaper]: Original specification of EVM.
-   [KEVM]: Specification of EVM in K.

For more information about [K Framework], refer to these sources:

-   [K Tutorial]: Example simple (and complex) languages in K.

[Autoconf]: <http://www.gnu.org/software/autoconf/>
[Bison]: <https://www.gnu.org/software/bison/>
[eei]: <eei.md>
[EEI]: <https://github.com/ewasm/design>
[EVM Yellowpaper]: <https://github.com/ethereum/yellowpaper>
[Flex]: <https://github.com/westes/flex>
[git]: <https://git-scm.com/>
[Homebrew]: <https://brew.sh/>
[K Framework]: <http://kframework.org>
[K Tutorial]: <https://github.com/kframework/k/tree/master/k-distribution/tutorial>
[libmpfr]: <http://www.mpfr.org/>
[libtool]: <https://www.gnu.org/software/libtool/>
[Opam]: <https://opam.ocaml.org/doc/Install.html>
[OpenJDK]: <http://openjdk.java.net/>
[pandoc]: <https://pandoc.org>
[Z3]: <https://github.com/Z3Prover/z3>
