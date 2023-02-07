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

## Dprint

Use dprint as below

```console
$ dprint --config dprint-ci.json check
$ dprint --config dprint-ci.json fmt
```

Providing 2 config files. For the purpose below

- [dprint-ci.json](dprint-ci.json) - Except ruby for faster run
- [dprint.json](dprint.json) - Includes rubocop integration. Just using in vscode

## Rubocop

Using rubocop as a formatter. So recommend to execute it with servermode before editting code to reduce time.

```console
$ bundle exec rubocop --start-server
```

Vscode tasks does not include it because of executed server process will exists even after closing vscode.\
Please manually kill it as below.

```console
$ bundle exec rubocop --stop-server
```

See [microsoft/vscode#65986](https://github.com/microsoft/vscode/issues/65986) for further detail.

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
