# First smart contracts with Cairo and HER DAO ![PRs Welcome](https://img.shields.io/badge/PRs-welcome-green.svg) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/auditless/cairo-template/blob/main/LICENSE) <a href="https://github.com/auditless/cairo-template/actions/workflows/test.yaml"> <img src="https://github.com/auditless/cairo-template/actions/workflows/test.yaml/badge.svg?event=push" alt="CI Badge"/> </a>

[**Slides for the workshop**](https://docs.google.com/presentation/d/e/2PACX-1vQAsFzOhJSWroZzy2I2D9vbg1tHJNh8D9-ETrCwITX8Q33mfIVQetk0Z_ppbP_Xd2SIOcwbPxv_UiEm/pub?start=false&loop=false&delayms=3000)

A workshop for building smart contracts with Cairo 1.0.

## How it works

- No submodules, forks or other heavy machinery

## Installing dependencies

### Step 1: Install Cairo 1.0

If you are on an x86 Linux system and able to use the release binary,
you can download Cairo here https://github.com/starkware-libs/cairo/releases.

For everyone, else, we recommend compiling Cairo from source like so:

```bash
# Install stable Rust
$ rustup override set stable && rustup update

# Clone the Cairo compiler in $HOME/Bin
$ mkdir ~/Bin
$ cd ~/Bin && git clone git@github.com:starkware-libs/cairo.git && cd cairo

# Generate release binaries
$ cargo build --all --release
```

**NOTE: Keeping Cairo up to date**

Now that your Cairo compiler is in a cloned repository, all you will need to do
is pull the latest changes and rebuild as follows:

```bash
$ cd ~/Bin/cairo && git fetch && git pull && cargo build --all --release
```

### Step 2: Add Cairo 1.0 executables to your path

```bash
export PATH="$HOME/Bin/cairo/target/release:$PATH"
```

**NOTE: If installing from a Linux binary, adapt the destination path accordingly.**

This will make available several binaries. The one we use is called `cairo-test`.

### Step 3: Install the Cairo package manager Scarb

Follow the installation guide in [Scarb's Repository](https://github.com/software-mansion/scarb).

Go to [Scarb's Releases](https://github.com/software-mansion/scarb/releases)

For MacOS installation:
```
 # Download `scarb-v0.1.0-rc.0-x86_64-apple-darwin.tar.gz`
 # extract file
 
 $ cd ~/Downloads/scarb-v0.1.0-rc.0-x86_64-apple-darwin/bin
 $ echo $PATH.       # to see if you have /usr/bin/local
 $ sudo cp scarb /usr/bin/local
 
 # if you do not have permissions
 $ xattr -d com.apple.quarantine /usr/bin/local/scarb
 
 # new tab
 $ scarb --version
```

### Step 4: Setup Language Server

#### VS Code Extension

- Disable previous Cairo 0.x extension
- Install the Cairo 1 extension for proper syntax highlighting and code navigation.
Just follow the steps indicated [here](https://github.com/starkware-libs/cairo/blob/main/vscode-cairo/README.md).

#### Cairo Language Server

From [Step 1](#step-1-install-cairo-10-guide-by-abdel), the `cairo-language-server` binary should be built and executing this command will copy its path into your clipboard.

```bash
$ which cairo-language-server | pbcopy
```

Update the `languageServerPath` of the Cairo 1.0 extension by pasting the path.

## License

[MIT](https://github.com/auditless/cairo-template/blob/main/LICENSE) © [Auditless Limited](https://www.auditless.com)
