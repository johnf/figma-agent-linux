# Figma Agent for Linux

[![CI](https://github.com/neetly/figma-agent-linux/actions/workflows/ci.yml/badge.svg)](https://github.com/neetly/figma-agent-linux/actions/workflows/ci.yml)

(a.k.a. Font Helper)

## Installation

```sh
bash -c "$(curl -fsSL https://raw.githubusercontent.com/neetly/figma-agent-linux/main/scripts/install.sh)"
```

### Arch Linux

```sh
paru -S --needed figma-agent-linux
systemctl --user enable --now figma-agent.socket
```

<details>
<summary><h3>Uninstallation</h3></summary>

```sh
systemctl --user disable --now figma-agent.{service,socket}
rm -rf ~/.local/share/figma-agent
rm -rf ~/.local/share/systemd/user/figma-agent.{service,socket}
```

</details>

## Features

- Support [Variable Fonts][]
- High Performance (Thanks to [Fontconfig][])

## Comparisons

|                            | Figma Agent for Linux | [Figma Linux Font Helper][] |
| -------------------------- | --------------------- | --------------------------- |
| [Variable Fonts][]         | ✔️                    | ❌                          |
| [XDG Base Directory][]     | ✔️                    | ✔️                          |
| [Fontconfig][] Integration | ✔️                    | ❌                          |
| Run as a non-root user     | ✔️                    | ✔️                          |

## Alternatives

Another option is to use [Wine][] to run the official `figma_agent.exe` binary.
I use this approach during development for the reverse engineering
proposal.

## Credit

This project was inspired by [Figma Linux Font Helper][].

[Variable Fonts]: https://www.figma.com/typography/variable-fonts/
[Fontconfig]: https://www.freedesktop.org/wiki/Software/fontconfig/
[XDG Base Directory]:
  https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
[Figma Linux Font Helper]:
  https://github.com/Figma-Linux/figma-linux-font-helper
[Wine]: https://www.winehq.org/
