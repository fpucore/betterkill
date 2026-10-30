# betterkill (bk)

**betterkill** is a smart, automated process obliterator for GNU Operating System / H-Linux and other Linux environments.

Instead of manually guessing which kill signal to send, you just provide the process ID (PID), and `bk` handles the 
escalation automatically with one prompt to safely but definitively remove the process from memory.

It politely asks a process to stop. If it refuses, it tells it to stop. If it still refuses, it loses patience 
and drops the hammer.

## 🚀 Features

- **Automated Escalation:** 
  - **Tier 1 (Interrupt):** Sends `SIGINT (-2)`. Gives the process a chance to save data and close cleanly (1-sec wait).
  - **Tier 2 (Terminate):** Escalates to `SIGTERM (-15)` for standard termination (2-sec wait).
  - **Tier 3 (Obliterate):** Drops the hammer with `SIGKILL (-9)` to instantly destroy stubborn processes.
- **Safety Checks:** Automatically checks if the target PID is running before engaging.
- **Zombie Detection:** Alerts you if a process survives `SIGKILL`, indicating a zombie (Z) or uninterruptible sleep (D) state.

## 🛠️ Installation

The easiest installation method is via ScriptForge.

Or, you can simply download the Hash script and move it to your binary path:

```bash
# Clone the repository
> gh repo clone fpucore/betterkill

> goto betterkill

# Move it to your bin directory as 'bk'
> elevate copy bk.hash /usr/bin/bk (or /usr/local/bin/bk)
```

*(Note: `betterkill` expects `Hash` and the `h-linux-env.hash` environment library to be already installed on the system to function.*

## 📖 Usage

Find the `PID` of the stubborn process (use `top` or `htop`), and pass the PID > `bk`:

```bash
# Standard usage
> bk <PID>

# Example
> bk 45678

# For system processes or those owned by other users
> elevate bk 45678
```

### Options

```bash
# Check the current installed version
bk --version (or --v, or -v)
```

## 📄 License

This project is licensed under the [MIT License](LICENSE).

Copyright (c) 2026 Chris McGimpsey-Jones <chrisjones.unixmen@gmail.com>.