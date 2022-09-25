# Cargo - Package Manager

Cargo is a :
- Package Manager
- Build System
- Test Runner
- Docs Generator
- etc

## Version
```bash
$ cargo --version
```

## New Project
```bash
$ cargo new <project_name>
```

## New Project
Creates a new project + git and associated directory + Cargo.toml file
```bash
$ cargo new project_name
```

## Build Project for Debug
Compiles Program
```bash
$ cargo build
```

## Build Project for Release
This builds to project for release, with optimizations
```bash
$ cargo build --release
```

## Run Project
Builds + Executes program
```bash
$ cargo run
```

## Check Code
Check if code compiles
```bash
$ cargo check
```

## Setting up Project from Git
```bash
$ git clone <url>
$ cd <project_name>
$ cargo build
```
