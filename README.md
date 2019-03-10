# git-profile

A POSIX-compliant implementation of git-profile subcommand

## Installation

```
$ curl -sSL -o /usr/local/bin/git-profile https://git.io/git-profile && chmod +x /usr/local/bin/git-profile
```

## Uninstallation

```
$ rm /usr/local/bin/git-profile
```

## Configuration

git-profile reads profiles from the shell file `~/.gitprofiles` ( can be controlled by setting the `GIT_PROFILES` environment variable), profiles are functions start with `profile_`, below is a sample which has two profiles (profile1 and profile2):

```shell
#!/usr/bin/env sh

# For more information about customizing git at
# https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration
profile_profile1() {
  git config user.name "profile1"
  git config user.email "profile1@mail.com"
}

profile_profile2() {
  git config user.name "profile2"
  git config user.email "profile2@mail.com"
}
```

In addition, below config is recommended for Git ([more information](https://git-scm.com/docs/git-config#git-config-useruseConfigOnly)):

```
$ git config --global user.useConfigOnly true
```

## Usage

```
$ git profile -h
usage: git profile [options] [profile_name]

Options:
  -h                      Print help information
  -l, --list              List all profiles
      --version           Print version information

Examples:
  1. List all profiles    $ git profile -l
  2. Switch to a profile  $ git profile profile1
```

## Change Log

See CHANGELOG [here](CHANGELOG.md)
