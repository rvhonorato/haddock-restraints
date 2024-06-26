# haddock-restraints

[![Crates.io Version](https://img.shields.io/crates/v/haddock-restraints)](https://crates.io/crates/haddock-restraints)
[![Crates.io Total Downloads](https://img.shields.io/crates/d/haddock-restraints)](https://crates.io/crates/haddock-restraints)
[![Crates.io License](https://img.shields.io/crates/l/haddock-restraints)](https://crates.io/crates/haddock-restraints)

[![tests](https://github.com/haddocking/haddock-restraints/actions/workflows/test.yml/badge.svg)](https://github.com/haddocking/haddock-restraints/actions/workflows/test.yml)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/cc008f968e394457ae63650cccfd27da)](https://app.codacy.com/gh/haddocking/haddock-restraints/dashboard?utm_source=gh&utm_medium=referral&utm_content=&utm_campaign=Badge_grade)

A standalone command-line application to generate restraints to be used in HADDOCK.

> Check [bonvinlab.org/haddock-restraints](https://bonvinlab.org/haddock-restraints) for a user guide.

## Commands

- [`tbl`: Generates a TBL file](https://www.bonvinlab.org/haddock-restraints/tbl.html)
- [`ti`: Generate true-interface restraints from a PDB file](https://www.bonvinlab.org/haddock-restraints/ti.html)
- [`restraint`: Generate Unambiguous restraints to keep molecules together during docking](https://www.bonvinlab.org/haddock-restraints/restraint.html)
- [`interface`: List residues in the interface](https://www.bonvinlab.org/haddock-restraints/interface.html)

## Planned features

- [x] Generate `.tbl` files from an input file (tbl command)
- [x] Define passive residues based on surface accessibility (tbl command - `surface_as_passive`)
- [x] Define passive residues around active ones (tbl command - `passive_from_active`)
- [x] Support for N interactors; 2-body, 3-body, 4-body, etc (tbl command)
- [x] Support for multiple interaction sites in the same interactor (tbl command)
- [x] Generate _true-interface_ restraints for benchmarking (ti command)
- [x] Create unambiguous restraints to keep molecules together during docking (restraint command)
- [x] Filter out buried residues (tbl command)
- [x] List residues in the interface (interface command)
- [ ] Template based restraints
- [ ] Specify atom subsets
- [ ] ~Generate random-restraints~ done via CNS

## Usage

### Install

> [Install Rust](https://www.rust-lang.org/tools/install) if you don't have it yet - later we will provide the execution binaries 🤓

```bash
cargo install haddock-restraints
```

### Execute

```bash
$ haddock-restraints -h
Generate restraints to be used in HADDOCK

Usage: haddock-restraints <COMMAND>

Commands:
  tbl        Generate TBL file from input file
  ti         Generate true-interface restraints from a PDB file
  restraint  Generate Unambiguous restraints to keep molecules together during docking
  interface  List residues in the interface
  help       Print this message or the help of the given subcommand(s)

Options:
  -h, --help     Print help
  -V, --version  Print version
```

## Troubleshooting

### `/usr/bin/ld: cannot find -lc++: No such file or directory`

```bash
sudo apt-get install libc++-dev libc++abi-dev
```

### `Unable to find libclang`

```bash
sudo apt-get install libclang-dev
```
