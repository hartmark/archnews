# archnews

Python utility for displaying [Arch news feed](https://www.archlinux.org/feeds/news/) in console.

I was looking for an utility that would quickly show the [Arch Linux](https://www.archlinux.org/) news feed
in command line before upgrading my system. Unfortunately I did not find any program that would suit my needs.
So I wrote my own and I took it also as a practice in Python programming.

Features:
 - It is written in pure Python 3, no extra dependencies are needed.
 - It wraps feed description to improve readability and tries to interpret HTML as nicely as possible.
 - It uses colors. (Can be turned off.)
 - Time is formatted according locale.
 - Supports tracking of unread messages.
 - Comes with a transparent `pacman` wrapper (called `archnews_wrap`), so one will never miss a news when doing `pacman -Syu`. (See [section Pacman wrapper](#pacman-wrapper) or a manual page.)
 - Many command line options! (See `--help` or manual page.)


## Installation

Because this is a tool specifically for Arch Linux, install it via [AUR](https://wiki.archlinux.org/index.php/Arch_User_Repository): https://aur.archlinux.org/packages/archnews2/

(Note: do NOT use directly the PKGBUILD file located inside this repository. It will NOT work!)

### Pacman wrapper

Utility `archnews` comes with a shell script called `archnews_wrap`. It just passes all its parameters to `pacman` unless parameters are `-Syu` (or its variant like e.g. `-Syyu`). In this case it invokes `archnews` with `--unread` option (and then `pacman` on user input).

`archnews_wrap` is designed to be used as shell alias for `pacman` like this:

```bash
alias sudo='sudo '  # This enables aliases for commands inside sudo.
alias pacman=archnews_wrap  # This invokes wrapper whenever pacman is called.
```

Thus you will never miss a news when doing system upgrade!


## How it looks in action

![screen of archnews in terminal](doc/archnew_in_action.gif)


## Contribution

I am willing to maintain and further develop the project, so any contribution (issues, ideas, pull requests) is welcome.
