# lmaocat

**lmaocat** is a simple, fast, and dependency-free Bash script that colorizes terminal output using your terminal's 16-color palette.
(Basically just lolcat - but with your terminal colors only.)

---

[2025-07-24 03-18-30_trimmed_0-02_0-48.webm](https://github.com/user-attachments/assets/d4155829-eb81-4dc6-ae18-28a08b64095d)


## Features

- Supports both **line-by-line** and **character-by-character** colorization
- Respects ANSI escape sequences (won’t corrupt output from tools like `sl`, `cbonsai`, `neofetch`, etc.)
- Randomized color order for each run
- Easily configurable group size (how many lines/chars per color)
- Works great with ASCII art, or shitpost pipelines
- Added Truecolor support with the --avg switch.
- Added grading for predictable usage of output.
- Added example tests for usage.

---

## Usage

```bash
lmaocat [OPTIONS]
```

It reads from standard input and colorizes the output.

### Options

| Option   | Description                                               |
| -------- | --------------------------------------------------------- |
| `-c [N]` | Character mode — group every N characters (default: 1)    |
| `-l [N]` | Line mode — group every N lines                           |
| `-b`     | Use background color instead of foreground                |
| `-g`     | Grade colors from light → dark (deterministic order)      |
| `--dull` | Skip color 0 (black) and 15 (white) in the palette        |
| `--avg`  | Enable truecolor output (RGB interpolation across groups) |
| `--test` | Run a visual test suite in all supported modes            |

> **Default:** character mode with 1 character per color (`-c 1`)
Keep in mind that the -l switch is very unpredictable with anything that clears/updates the terminal. It's only useful for simple stdin values.

---

## Examples

### Pipe `ls` output through lmaocat
```bash
ls | lmaocat
```

### Colorize `neofetch` with grouped lines
```bash
neofetch | lmaocat -l 2
```

### Use background colors instead
```bash
cbonsai -l | lmaocat -b
```

### Skip black & white colors
```bash
sl | lmaocat --dull
```

### Group 5 characters per color
```bash
echo "Listen to My Chemical Romance" | lmaocat -c 5
```

---

## Why Bash?

UwU

---

