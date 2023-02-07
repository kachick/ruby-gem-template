# How to contribute

- Reporting bugs
- Suggesting features
- Creating PRs

Welcome all of the contributions!

## Setup

Needs your ruby and [dprint](https://dprint.dev/) for development.\
If you are using [Nix](https://nixos.org/) package manager, [the definition](default.nix) is included.

```console
$ git clone git@github.com:kachick/my_new_library.git
$ cd ./my_new_library
$ nix-shell
$ dprint --version
$ bundle install || bundle update
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
