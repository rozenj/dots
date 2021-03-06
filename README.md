# Screenshots:

# ![Current setup](https://raw.githubusercontent.com/rozenj/dots/master/extras/scrot/2020-10-25-012729_2560x1440_scrot.png)

# Required configuration:

In `~/.config/chezmoi/chezmoi.toml` set:

- **machine_type** - to one of `desktop`, `server`, `laptop`
- **browser** - path to browser

```
[data]
    machine_type = "desktop"
    browser = "/usr/bin/firefox"
```

Run [`extras/bootstrap/configure.sh`](extras/bootstrap/configure.sh) `<machine_type>` `<browser>` to
apply config
`extras/bootstrap/configure.sh laptop firefox firefox.desktop`
___

#### TODO:

- auto configure crontab - backup
- https://stackoverflow.com/a/38980986/8156320

Zsh execution:

|  |Interactive login |Interactive non-login|Script|
|-----------------|-----------|-----------|------|
|/etc/zshenv     |    A      |    A      |  A   |
|~/.zshenv       |    B      |    B      |  B   |
|/etc/zprofile   |    C      |           |      |
|~/.zprofile     |    D      |           |      |
|/etc/zshrc      |    E      |    C      |      |
|~/.zshrc        |    F      |    D      |      |
|/etc/zlogin     |    G      |           |      |
|~/.zlogin       |    H      |           |      |
|~/.zlogout      |    I      |           |      |
|/etc/zlogout    |    J      |           |      |

Bash execution:

|  |Interactive login |Interactive non-login|Script|
|-----------------|-----------|-----------|------|
| /etc/profile    |   A       |           |      |
| ~/.bash_profile |   B1      |           |      |
| ~/.bash_login   |   B2      |           |      |
| ~/.profile      |   B3      |           |      |
| /etc/bash.bashrc|           |    A      |      |
| ~/.bashrc       |           |    B      |      |
| BASH_ENV        |           |           |  A   |
| ~/.bash_logout  |    C      |           |      |

Bash is not supported
