# Environment

## Homebrew

Homebrew is a package manager for Mac OS X that installs the stuff you need that is not included by Apple.

  * [Install Homebrew](https://github.com/Homebrew/brew/blob/master/docs/Installation.md)
  * [Frequently Asked Questions](https://github.com/Homebrew/brew/blob/master/docs/FAQ.md)
  * [Tips and Tricks](https://github.com/Homebrew/brew/blob/master/docs/Tips-N'-Tricks.md)
  * [Gems, Eggs and Perl Modules](https://github.com/Homebrew/brew/blob/master/docs/Gems,-Eggs-and-Perl-Modules.md)

### Common Packages

  * git
  * git-ssh
  * git-flow
  * node
  * rbenv
  * ruby-build
  * drush
  * wget
  * percona-server
  * cmake
  * composer
  * n98-magerun
  * n98-magerun2

```bash
$ brew install git git-flow git-ssh wget curl mcrypt percona-server node composer drush n98-magerun n98-magerun2
```

#### MySQL (`percona-server`)

Refer to the percona-server info (`brew info percona-server`) for more details, but generally you will need to do the following things:

1. Initialize the MySQL data directory
2. Run `mysql_secure_installation` to remove the test databases, set a new `root` user password, etc.
3. Have MySQL start on startup or reboots

```bash
# initalize the MySQL data directory
# ------------------------------
# Note: this will create a temporary root user password
# that you will need to keep track of until
# you run the `mysql_secure_installation`
# ------------------------------
$ mysqld --initialize --datadir=/usr/local/var/mysql --user=<YOUR_OSX_USER_HERE>

# Set new `root` user password and remove test databases.
# Follow the prompts and questions
$ mysql_secure_installation

# Start MySQL on OS X startup/reboots
$ brew services percona-server start
```

#### Install PHP (5.6 and 7.0)

As a developer you will most often need PHP 5.6 and PHP 7.0 to cover recent projects (1-2 years old) and support for new projects and frameworks that are capable of supporting PHP 7+

```bash
# Tap the homebrew/php libraries for more
# PHP versions and extensions
$ brew tap homebrew/php

# If you use Apache instead of NGINX, add `--with-apache` option
$ brew install php56 --with-homebrew-curl --with-imap --with-pear
$ brew install php56-mcrypt php56-intl php56-ioncubeloader

# Unlink PHP 5.6 before installing PHP 7.0
$ brew unlink php56

# If you use Apache instead of NGINX, add `--with-apache` option
$ brew install php70 --with-homebrew-curl --with-imap --with-pear
$ brew install php70-mcrypt php70-intl php70-ioncubeloader
```

After your PHP 5.6 and 7.0 versions are installed you can switch between them by using `brew unlink` and `brew link` commands. If you are using NGINX with PHP-FPM, make sure you stop your PHP-FPM instances before switching PHP versions.

**Examples:**

```bash
# Switch PHP version from 7.0 to 5.6
$ php70-fpm stop
$ brew unlink php70
$ brew link php56
$ php56-fpm start
```

If you forget where your PHP/PHP-FPM configuration files are simply use `brew info` to get the details of a package.

```
$ brew info php56
$ brew info php70
```

#### Ruby (via rbenv)

We use Ruby for some custom projects but most often it is used as a utility tool, especially for deploying projects to servers via [Capistrano](http://capistranorb.com/).  Sites hosted on Pantheon or other container-based environments (i.e., Platform.sh, docker, etc.) are the exclusion.

Use [**rbenv**](https://github.com/rbenv/rbenv) to manage multiple versions of Ruby. **DO NOT USE RVM.  Josh will not help you if you use RVM**.

```bash
$ brew install rbenv ruby-build rbenv-bundle-exec
```

**Post `rbenv` install steps:**

1. Run `rbenv init` and follow the instructions
2. Avoid ever having to use `rbenv rehash` again after installing ruby gems with `rbenv-gem-rehash`: <br/><br/> `$ git clone https://github.com/sstephenson/rbenv-gem-rehash.git ~/.rbenv/plugins/rbenv-gem-rehash`<br/><br/>
3. Install an updated version of ruby: `$ rbenv install 2.3.1`
4. Set a global version of ruby to use: `$ rbenv global 2.3.1`
4. Install common gems: `$ gem install bundler capistrano`


## Pantheon

Pantheon is our hosting partner for most of our Drupal or WordPress projects. Their setup gives us/client access to three environments (dev/test/live) per account and has a built-in git workflow.

  * [Create an Account](https://pantheon.io/register)
  * [Getting started with Pantheon](https://pantheon.io/docs/tags/getting-started)
