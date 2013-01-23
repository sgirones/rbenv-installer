# rbenv installer

This tool is used to install `rbenv` and some plugins. It also provides 
scripts to install required software to be able to compile **Ruby**.

Installed plugins are `rbenv-vars`, `ruby-build` & `rbenv-installer`.

Once executed, the script makes available:

 - the `rbenv` [commands](https://github.com/sstephenson/rbenv#command-reference)
 - the `rbenv-vars` plugin [commands](https://github.com/sstephenson/rbenv-vars)
 - the `ruby-build` plugin [commands](https://github.com/sstephenson/ruby-build)

as well as the following `rbenv-installer` plugin specific commands:

 - rbenv cleanup
 - rbenv bootstrap
 - rbenv bootstrap-ubuntu-10-04
 - rbenv bootstrap-ubuntu-12-04
 - rbenv plugin
 - rbenv plugins
 - rbenv update

## Before Installing

Install `git` and `curl`:

- Git
- Curl


# Managing rbenv and rbenv-installer plugins

## Installing rbenv

### For users

Install [rbenv] and friends by running:

    curl https://raw.github.com/fesplugas/rbenv-installer/master/bin/rbenv-installer | bash

The friends installed by default are the plugins:

 - [sstephenson:rbenv-vars](https://github.com/sstephenson/rbenv-vars)
 - [sstephenson:ruby-build](https://github.com/sstephenson/ruby-build)

### For developers

You can test your in-development version of the rbenv-installer (on Github):

    rm -rf ~/.rbenv/plugins
    export RBENV_INSTALLER_AUTHOR=taqtiqa-mark
    export RBENV_INSTALLER_BRANCH=feature/plugin
    curl -L https://raw.github.com/$RBENV_INSTALLER_AUTHOR/rbenv-installer/$RBENV_INSTALLER_BRANCH/bin/rbenv-installer|bash

Similarly, you can set the `RBENV_AUTHOR` and `RBENV_PLUGIN_AUTHOR` Github names.
Both of these default to [sstephenson](https://github.com/sstephenson).

Default behavior is to install from the `master` branches. To install from:

 - the `abc` branch of [sstephenson/rbenv](https://github.com/sstephenson/rbenv)
 - the `xyz` branch of [fesplugas/rbenv-installer](https://github.com/fesplugas/rbenv-installer)
 - the `klm` branch of the plugins [sstephenson:rbenv-vars](https://github.com/sstephenson/rbenv-vars) and [sstephenson:ruby-build](https://github.com/sstephenson/ruby-build)

````
export RBENV_BRANCH=abc
export RBENV_INSTALLER_BRANCH=xyz
export RBENV_PLUGIN_BRANCH=klm
curl https://raw.github.com/fesplugas/rbenv-installer/master/bin/rbenv-installer | bash
````

## Updating rbenv

To update `rbenv` and the plugins provided by this installer run:

    rbenv update

# Managing a Ruby

## Installing

Install Ruby `1.9.3-p374` and make it global:

    rbenv install 1.9.3-p374
    rbenv global 1.9.3-p374

See [here](https://github.com/sstephenson/ruby-build) for more details.

<<<<<<< HEAD
Updating 
--------
=======
## Uninstalling
>>>>>>> f40caf5d10660f89e0a4fadf4d9f93ff5b895805

Uninstall Ruby `1.9.3-p194`:

    rbenv uninstall 1.9.3-p194

See [here](https://github.com/sstephenson/ruby-build) for more details.

# Managing a Ruby's Gems
## Cleanup

Remove all the gems for the current Ruby:

    rbenv cleanup

See [Bundler](http://gembundler.com/) and [RubyGems](http://rubygems.org/pages/download) for additional tooling.

# Managing Rbenv Plugins
## Installing (Updating) a plugin

### Example 1: Install then update+install

Default behavior is to install from the `master` branch.
Install the `rbenv-vars` plugin from [sstephenson/rbenv-vars](https://github.com/sstephenson/rbenv-vars):

    rbenv plugin sstephenson:rbenv-vars

Install `ruby-build` plugin and update `rbenv-vars` plugin (installed above):

    rbenv plugins sstephenson:rbenv-vars sstephenson:ruby-build

### Example 2: Install from a specific branch

Install the `xyz` plugin from the `develop` branch of ABC's repository `xyz`:

    export RBENV_PLUGIN_BRANCH=develop
    rbenv plugin abc:xyz

## Bootstrap

If you are installing `rbenv` in Ubuntu you'll probably need to install
some required packages. You can use the provided `bootstrap` scripts.

    rbenv bootstrap-ubuntu-12-04
    rbenv bootstrap-ubuntu-10-04

To update `RubyGems` and install `bundler` and `rake`:

    rbenv bootstrap


## About rbenv

**rbenv** source code is available at <https://github.com/sstephenson/rbenv>

[rbenv]: https://github.com/sstephenson/rbenv
