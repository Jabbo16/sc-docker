# BASIL SC-Docker

[![Build Status](https://travis-ci.org/basil-ladder/sc-docker.svg?branch=master)](https://travis-ci.org/basil-ladder/sc-docker)

This repository hosts the modified [sc-docker](https://github.com/Games-and-Simulations/sc-docker) used for running the [BASIL ladder](https://basil.bytekeeper.org/).

## Installation

See [installation instructions for Linux / Windows / Mac](INSTALL.md).

It should run well on new versions of major operating systems. It was tested on:

- Ubuntu 17.04 Zesty, `Linux 4.10.0-40-generic x86_64`
- Microsoft Windows 10 (64-bit)
- Mac OS Sierra 10.12.6 (64-bit, Mac mini)

Testing and reporting in other settings is very welcome!

## Usage

### Bots playing against each other

Launch headful play of [krasi0](http://sscaitournament.com/index.php?action=botDetails&bot=krasi0) and [CherryPi](https://sscaitournament.com/index.php?action=botDetails&bot=CherryPi) on default map.

    $ scbw.play --bots "krasi0" "CherryPi" --show_all

Create game on the server (VNC viewer on port 5900) and wait for bots to join the game.

### Play against a bot

    $ scbw.play --bots "PurpleWave" --human

Select a map, specify your race, and wait for bot(s) to join the game :)

You can put the RealVNC client to fullscreen and play comfortably.

(Although you might want to change your screen resolution to 800x600)

The GUI is going to be probably slower than normal game due to streaming via VNC.

It is however possible to play the game from the host if you have Windows,
but it is [more complicated setup](USAGE.md#play-on-the-host).

See [more usage examples](USAGE.md).

## Known limitations

- Headful mode needs to specify the map manually due to "Unable to distribute map" bug.
- Works only for BWAPI 3.7.4, 3.7.5, 4.1.2, 4.2.0 and 4.4.0

## Specification

- StarCraft 1.16.1 game from ICCUP (no need for special installs!)
- BWAPI 3.7.4, 3.7.5, 4.1.2, 4.2.0, 4.4.0
- SSCAI maps pack with BWTA/BWTA2 caches
- [Amazon Corretto 8](https://aws.amazon.com/en/corretto/)
- bwheadless `v0.1` with LF3 patch
- Wine 5
- base image `ubuntu:bionic`
- uses special [tournament module (TM)](github.com/Games-and-Simulations/sc-tm)

## Contributing

Pull requests are welcome! There are still many things to do, especially from [todo list](TODO.md).

## Citations

If you use `sc-docker` in your (academic) work, please cite [our Technical Report](https://arxiv.org/abs/1801.02193):

    @misc{sustr2018multi,
        Author = {Michal \v{S}ustr and Jan Mal\'{y} and Michal \v{C}ertick\'{y}},
        Title = {{Multi-platform Version of StarCraft: Brood War in a Docker Container: Technical Report}},
        Year = {2018},
        Eprint = {arXiv:1801.02193},
    }
