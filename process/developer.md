# Development Guide

- [Development Guide](#contributor-guide)
  - [Welcome](#welcome)
  - [Pre submit flight checks](#pre-submit-flight-checks)
  - [GitHub Workflow](#gitHub-workflow)

## Welcome

This document is the canonical source of truth for things like supported
toolchain versions for building projects in the [symblai](https://github.com/symblai) org.

Please submit an [issue] on GitHub if you
* Notice a requirement that this doc does not capture.
* Find a different doc that specifies requirements (the doc should instead link here).

Development branch requirements will change over time, but release branch
requirements are frozen.

## Pre submit flight checks

Determine whether your issue or pull request is improving project
architecture or whether it's simply fixing a bug.

If you need a diagram, add it. SEPARATE the description of the problem (e.g. Y
is a critical component that is too slow for an SLA that we care about) from the
solution (e.g. make X faster).

No issue should take more than 5 minutes to check for sanity (even the busiest of
reviewers can spare 5 minutes to review a patch that is thoughtfully justified).

### Is this just a simple bug fix?

Simple bug patches are easy to review. Bug fixes don't usually require a lot of
extra testing, but please update the unit tests so they catch the bug!

### Is this an architecture improvement?

Some examples of "Architecture" improvements include:

- Adding a new feature or making a feature more configurable or modular.
- Improving test coverage.
- Decoupling logic or creation of new utilities.
- Making code more resilient (sleeps, backoffs, reducing flakiness, etc.).

These sorts of improvements are easily evaluated, especially when they decrease
lines of code without breaking functionality. That said, please explain exactly
what you are 'cleaning up' in your Pull Request so as not to waste a reviewer's
time.

If you're making code more resilient, include tests that demonstrate the new
resilient behavior.

### Is this a performance improvement?

Performance bug reports MUST include data that demonstrates the bug. Without
data, the issue will be closed.

Examples of how NOT to suggest a performance bug (these lead to a long review
process and waste cycles):

- We *should* be doing X instead of Y because it *might* lead to better performance.
- Doing X instead of Y would reduce calls to Z.

The above statements have no value to a reviewer because neither is backed by
data. Writing issues like this lands your PR in a no-man's-land and waste your
reviewers' time.

Examples of possible performance improvements include (remember, you MUST
document the improvement with data):

- Improving a caching implementation.
- Reducing calls to functions which are O(n^2)
- Changing the value of default parameters for processes, or making those values 'smarter'.
- Parallelizing a calculation that needs to run on a large set objects.

These issues should always be submitted with (in decreasing order of value):

- A golang Benchmark test.
- A hand-instrumented timing test (i.e. adding some logs into the controller manager).

Since performance improvements can be empirically measured, you should follow
the "scientific method" of creating a hypothesis, collecting data, and then
revising your hypothesis. The above issues do this transparently, using figures
and data rather than conjecture. Notice that the problem is analyzed and a
correct solution is created before a single line of code is reviewed.

### Preparing Your Local Operating System

Where needed, each piece of required software will have separate
instructions for Linux, Windows, or macOS.

#### Setting Up Windows

If you are running Windows, you will need to use one of two methods
to set up your machine for development. To figure out which
method is the best choice, you will first need to determine which version of
Windows you are running. To do this, press **Windows logo key + R**,
type **winver**, and click **OK**. You may also enter the `ver` command at
the Windows Command Prompt.

TODO

#### Setting Up macOS

This assumes you are using GNU command line tools, you will need to
install those tools on your
system. [Follow these directions to install the tools](https://ryanparman.com/posts/2019/using-gnu-command-line-tools-in-macos-instead-of-freebsd-tools/).
In particular, this command installs the necessary packages:

```sh
brew install coreutils ed findutils gawk gnu-sed gnu-tar grep make jq
```

You will want to include this block or something similar at the end of
your `.bashrc` or shell init script:

```sh
GNUBINS="$(find `brew --prefix`/opt -type d -follow -name gnubin -print)"

for bindir in ${GNUBINS[@]}
do
  export PATH=$bindir:$PATH
done

export PATH
```

This ensures that the GNU tools are found first in your path. Note
that shell init scripts work a little differently for
macOS. [This article can help you figure out what changes to make.](https://scriptingosx.com/2017/04/about-bash_profile-and-bashrc-on-macos/)

### Installing Required Software

#### GNU Development Tools 

Development helper scripts require an up-to-date GNU
development tools environment. The method for installing these tools
varies from system to system.

##### Installing on Linux

All Linux distributions have the GNU tools available. The most popular
distributions and commands used to install these tools are below.

- Debian/Ubuntu
  ```sh
  sudo apt update
  sudo apt install build-essential
  ```
- Fedora/RHEL/CentOS
  ```sh
  sudo yum update
  sudo yum groupinstall "Development Tools"
  ```
- OpenSUSE
  ```sh
  sudo zypper update
  sudo zypper install -t pattern devel_C_C++
  ```
- Arch
  ```sh
  sudo pacman -Sy base-devel
  ```

Once you have finished, confirm that `gcc` and `make` are installed.

##### Installing on macOS

Some of the build tools were installed when you prepared your system
with the GNU command line tools earlier. However, you will also need
to install the
[Command Line Tools for Xcode](https://developer.apple.com/library/archive/technotes/tn2339/_index.html).

#### Docker

Development requires Docker to run certain verifications. To
install Docker in your development environment,
[follow the instructions from the Docker website](https://docs.docker.com/get-docker/).

**Note:** If you are running macOS, make sure that `/usr/local/bin` is
in your `PATH`.

#### jq

Some of the helper scripts require `jq`, a command-line JSON processor, to be
installed in your development environment. The
[jq installation guide](https://stedolan.github.io/jq/download/)
provides detailed instructions for supported platforms.

#### node.js

TODO

#### Go

Some of Symbl's GitHub projects are written in [Go](http://golang.org).
If you have a need for a Go development environment, please follow the instructions
in the [Go Getting Started guide](https://golang.org/doc/install).

Confirm that your `GOPATH` and `GOBIN` environment variables are
correctly set as detailed in
[How to Write Go Code](https://golang.org/doc/code.html) before
proceeding.

#### Cloning Projects in the Symblai Organization

You are now ready to clone projects in the [symblai](https://github.com/symblai) org. See the [GitHub Workflow](/process/github-workflow.md) document for instructions.

##### BASH version requirement

If you are running on Linux or macOS, you will need bash version installed to be >4.3.

## GitHub Workflow

To check out code to work on, please refer to [this guide](/process/github-workflow.md).

[issue]: https://github.com/symblai/community/issues
