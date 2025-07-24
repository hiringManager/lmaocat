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

---

## Usage

```bash
lmaocat [OPTIONS]
```

It reads from standard input and colorizes the output.

### 🔧 Options

| Flag        | Description                                               |
|-------------|-----------------------------------------------------------|
| `-c [N]`    | Character mode (default). Group N characters per color    |
| `-l [N]`    | Line mode. Group N lines per color                        |
| `-b`        | Use **background** color instead of foreground            |
| `--dull`    | Excludes terminal colors 0 and 15 (often black and white) |

> **Default:** character mode with 1 character per color (`-c 1`)

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

Because fuck you, that's why.

---

