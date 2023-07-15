# How to contribute

- Reporting bugs
- Suggesting features
- Creating PRs

Welcome all of the contributions!

## Setup

Needs your ruby, which is a supported version, and some external tools for development.\
Author is using [Nix](https://nixos.org/), and put the [definition](flake.nix).

```console
$ git clone git@github.com:kachick/my_new_library.git
$ cd ./my_new_library
$ nix develop # Or `direnv allow`
$ dprint --version
$ bundle install || bundle update
```

## Dprint

Using [dprint](https://dprint.dev/) for common formatter except ruby.

```console
$ dprint check
$ dprint fmt
...
```

## Rubocop

Using rubocop as a ruby formatter.

```console
$ bundle exec rubocop
$ bundle exec rubocop --autocorrect
...
```

## Feel the latest version with REPL

```console
$ ./bin/console
Starting up IRB with loading with latest code
```

## Check list after changes

If you try to add/change/fix features, please update and/or confirm core feature's tests are not broken.

```console
$ bundle exec rake
$ echo $?
0
```

If you want to run partially tests, test-unit can take some patterns(String/Regexp) with the naming.

```console
$ bundle exec rake test TESTOPTS="-v -n'/test_.*foobar/i'"
Runs test cases only for matched the pattern
```

CI includes signature check, lint, if you want to check them in own machine, below command is the one.

But please don't hesitate to send PRs even if something fail in this command!

```console
$ bundle exec rake simulate_ci
$ echo $?
0
```
