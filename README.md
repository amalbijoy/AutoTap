# AutoTap

> A lightweight Python auto-clicker with configurable click rates, mouse buttons, global hotkeys, and runtime statistics.

## Features

- Start / stop clicking with a global hotkey
- Pause / resume controls
- Emergency stop with `Esc`
- Left, right, or middle mouse button
- Delay-based or clicks-per-second (CPS) configuration
- Runtime statistics: total clicks, elapsed time, and average CPS
- Graceful shutdown
- Threaded click loop so the keyboard listener remains responsive
- CLI argument parsing with `--delay`, `--cps`, and `--button`

## Installation

Python 3.8+ is recommended.

Install the dependency:

```bash
python -m pip install pynput
```

## Usage

Start the program:

```bash
python AutoTap.py
```

Set a target click rate:

```bash
python AutoTap.py --cps 100
```

Set a delay and mouse button:

```bash
python AutoTap.py --delay 0.05 --button right
```

### Command-line options

| Option | Purpose |
|---|---|
| `--delay`, `-d` | Delay between clicks in seconds |
| `--cps`, `-c` | Clicks per second; takes precedence over `--delay` |
| `--button`, `-b` | `left`, `right`, or `middle` mouse button |

### Runtime controls

| Key | Action |
|---|---|
| `1` | Start / stop |
| `2` | Pause / resume behavior |
| `3` | Show statistics |
| `0` | Exit |
| `Esc` | Emergency stop |

## Notes

The click loop enforces a minimum delay when the delay option is used. Very high click rates can still place significant load on the input system or target application.

`pynput` also depends on the host operating system's input permissions and desktop environment, so behavior can vary by platform.

This tool is intended for personal automation, testing, and other permitted use. Do not use it to bypass application rules or interfere with systems you do not control.

## Development

A GitHub Actions workflow provides a basic Python compile check. There is not currently a comprehensive automated GUI/input test suite.

## License

See [LICENSE](LICENSE).
