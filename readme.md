# WSL Ubuntu-24.04 Setup Guide with Go, Rust, and Zig
![WSL Ubuntu-24.04](setup.png)

This guide walks you through setting up Ubuntu-24.04 on Windows Subsystem for Linux (WSL), along with installing and configuring Go, Rust, and Zig programming languages. This comprehensive setup will provide you with a robust development environment for multiple programming paradigms.

## Overview
- WSL Ubuntu-24.04 installation
- Essential development tools and libraries
- Zsh and Oh My Zsh for an enhanced shell experience
- Go programming language setup
- Rust programming language installation
- Zig programming language setup

### Step-by-Step Installation

1. **Update WSL and Install Ubuntu-24.04:**
    ```bash
    wsl --install Ubuntu-24.04
    ```

2. **Update Packages:**
    ```bash
    sudo apt update
    ```

3. **Install Build Essentials:**
    ```bash
    sudo apt install build-essential
    ```

4. **Install Dependencies (libssl-dev, libcurl4-openssl-dev):**
    ```bash
    sudo apt install -y libssl-dev libcurl4-openssl-dev
    ```

5. **Install Zsh:**
    ```bash
    sudo apt install zsh
    ```

6. **Install Oh My Zsh:**
    ```bash
    sh -c "$(wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
    ```

7. **Upgrade Installed Packages:**
    ```bash
    sudo apt upgrade -y
    ```

8. **Download and Install Go (Golang):**
    Go is a statically typed, compiled programming language designed at Google.
    ```bash
    wget https://go.dev/dl/go1.22.5.linux-amd64.tar.gz
    sha256sum go1.22.5.linux-amd64.tar.gz
    sudo tar -C /usr/local -xvf go1.22.5.linux-amd64.tar.gz
    echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.zshrc && source ~/.zshrc
    go version
    ```

9. **Install Rust:**
    Rust is a systems programming language that runs blazingly fast, prevents segfaults, and guarantees thread safety.
    ```bash
    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
    . "$HOME/.cargo/env"
    ```

10. **Verify Rust Installation:**
    ```bash
    rustc --version
    cargo --version
    ```

11. **Download and Install Zig:**
    Zig is a general-purpose programming language and toolchain for maintaining robust, optimal, and reusable software.
    ```bash
    wget https://ziglang.org/download/0.13.0/zig-linux-x86_64-0.13.0.tar.xz
    sudo tar -C /usr/local -xvf zig-linux-x86_64-0.13.0.tar.xz
    sudo mv /usr/local/zig-linux-x86_64-0.13.0.tar.xz /usr/local/zig
    echo 'export PATH=$PATH:/usr/local/zig' >> ~/.zshrc && source ~/.zshrc
    ```

### Verification
Ensure all languages are correctly installed:

- **Verify Go Installation:**
    ```bash
    go version
    ```

- **Verify Zig Installation:**
    ```bash
    zig version
    ```

- **Verify Rust Installation:**
    ```bash
    rustc --version
    cargo --version
    ```

## Next Steps
After completing this setup, you'll have a fully functional WSL Ubuntu-24.04 environment with Go, Rust, and Zig ready for development. 
