# Tools

## Terminal

Terminal is the built-in app for MacOS that allows you to interactive with your computer via the command line.

  * [Introduction](http://blog.teamtreehouse.com/introduction-to-the-mac-os-x-command-line)
  * [iTerm2](https://www.iterm2.com) - Terminal replacement app that has a lot of useful/cool features

## Terminus

Terminus is Pantheon's Command Line Interface (CLI), providing equivalent functionality to the Pantheon Web Dashboard and easier scripting.

  * [Installation and Documentation](https://github.com/pantheon-systems/terminus)

## Git

  * [Git basics and Resources](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)
  * [Github](https://github.com)
  * [CodeSchool.com Free Course - Try Git](https://www.codeschool.com/courses/try-git)

## Browser Tools/Plugins

#### Firefox

  * [Firebug](http://getfirebug.com)
  * [Web Developer Toolbar](https://addons.mozilla.org/en-US/firefox/addon/web-developer)
  * [Performance Analyser](https://addons.mozilla.org/en-US/firefox/addon/performance-analyser)

#### Chrome

  * [Inspector Guide/Resource](https://developer.chrome.com/devtools)
  * [Web Developer Toolbar](https://chrome.google.com/webstore/detail/web-developer/bfbameneiokkgbdmiekhjnmfkcnldhhm)
  * [Performance Analyser](https://chrome.google.com/webstore/detail/performance-analyser/djgfmlohefpomchfabngccpbaflcahjf)

#### Safari

  * Nobody uses Safari for development and you shouldn't either.

#### Internet Explorer

  * [IE Tester - Browserstack](https://www.browserstack.com)

## iOS simulator (xcode)

An application built into Xcode that emulates iOS on your local machine. This is used for app building but can be handy when testing responsive sites and how things render on specific devices/screen sizes.

  * [Getting Started](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/iOS_Simulator_Guide/GettingStartedwithiOSSimulator/GettingStartedwithiOSSimulator.html)

#### Add shortcut to your dock

  1. Go to **Applications -> Xcode**. Right click and select **Show Package Contents**
  2. Go to **Developer -> Applications -> Simulator**. Double click to launch.
  3. Once launched, right click on the icon in the dock and select **Keep in dock**.

## Sequel Pro

A database management application for MacOS. Simple GUI for common database tasks like importing, exporting, user management, and DB creation.

  * [Download](https://www.sequelpro.com/)
  * OR install with Homebrew Cask:

 ```bash
 $ brew tap caskroom/cask
 $ brew cask install sequel-pro
 ```

## Sublime/IDE (themes, plugins, workflow)

  * plugins/addons
  * workflow
  * themes

 **Install with Homebrew Cask**

```bash
$ brew cask install sublime-text3
```

## Atom Text Editor

#### Reference:

  * [Atom website](https://atom.io/)
  * [Packages](https://atom.io/packages)
  * [Themes](https://atom.io/themes)
  * [Documentation](https://atom.io/docs)

#### Install with Homebrew Cask

```bash
$ brew cask install atom
```

## Sketch

A MacOS application specific for interface building. AAI produces designs using this application so assets may need to be retrieved from these files from time to time.

  * [Sketch Website](https://www.sketchapp.com/)
  * [Documentation](https://www.sketchapp.com/learn/documentation/)

## Node and the node package manager

NodeJS and it's companion package manner are great tools for supplementing local development (i.e., grunt, gulp, sass, etc) and in some cases we use it for custom applications.

* [NodeJS website](https://nodejs.org/)
* [npm website](https://www.npmjs.com/)
  - [Documentation](https://docs.npmjs.com/)

#### Install with Homebrew

```bash
# installation of node will also install npm
$ brew install node
```

#### Common packages we use

+ bower
+ gulp
+ node-sass

## Bower

From [Bower's website](https://bower.io/)

> Web sites are made of lots of things — frameworks, libraries, assets, and utilities. Bower manages all these things for you.
>
> Keeping track of all these packages and making sure they are up to date (or set to the specific versions you need) is tricky. Bower to the rescue!
>
> Bower can manage components that contain HTML, CSS, JavaScript, fonts or even image files. Bower doesn’t concatenate or minify code or do anything else - it just installs the right versions of the packages you need and their dependencies.
>
> To get started, Bower works by fetching and installing packages from all over, taking care of hunting, finding, downloading, and saving the stuff you’re looking for. Bower keeps track of these packages in a manifest file, bower.json. How you use packages is up to you. Bower provides hooks to facilitate using packages in your tools and workflows.
>
>Bower is optimized for the front-end. If multiple packages depend on a package - jQuery for example - Bower will download jQuery just once. This is known as a flat dependency graph and it helps reduce page load.

#### Install Bower

Bower requires `node`, `npm`, and `git`

```bash
# make sure bower dependencies are installed
$ brew install git node

# install bower via npm
$ npm install -g bower
```

#### Packages

```bash
# install packages
$ bower install <package>

# install a package and add it to bower.json
$ bower install <package> --save

# install specific version of a package
# and add it to bower.json
$ bower install <package>#<version> --save

# uninstall packages
$ bower uninstall <package>
```

**Never run Bower with sudo**. Bower is a user command; there is no need to execute it with superuser permissions.


## Gulp

[Gulp Website](https://github.com/gulpjs/gulp)

> #### What is gulp?
>
> + Automation - gulp is a toolkit that helps you automate painful or time-consuming tasks in your development workflow.
> + Platform-agnostic - Integrations are built into all major IDEs and people are using gulp with PHP, .NET, Node.js, Java, and other platforms.
> + Strong Ecosystem - Use npm modules to do anything you want + over 2000 curated plugins for streaming file transformations
> + Simple - By providing only a minimal API surface, gulp is easy to learn and simple to use

#### Install Gulp

Gulp requires `node` and `npm`

```bash
# 1. Install gulp globally:
# If you have previously installed a version of
# gulp globally, please run `npm rm --global gulp`
# to make sure your old version doesn't collide
# with gulp-cli.
$ npm install --global gulp-cli

# 2. Initialize your project directory:
$ npm init

# 3. Install gulp in your project devDependencies:
$ npm install --save-dev gulp
```

#### Examples/recipes

+ Sample [gulpfile.js](https://github.com/gulpjs/gulp#sample-gulpfilejs)
+ [Common recipes](https://github.com/gulpjs/gulp/tree/master/docs/recipes#recipes)


## Drush

> Drush is a command line shell and Unix scripting interface for Drupal. Drush core ships with lots of useful commands for interacting with code like modules/themes/profiles. Similarly, it runs update.php, executes sql queries and DB migrations, and misc utilities like run cron or clear cache. Drush can be extended by 3rd party commandfiles.

Basically, it's the Swiss Army Knife for Drupal.

+ [Drush website](http://www.drush.org/en/master/)

## Drupal Console

> The Drupal Console is a suite of tools run from a command line interface (CLI) to generate boilerplate code and interact with a Drupal 8 installation. From the ground up, it has been built to utilize the same modern PHP practices which were introduced in Drupal 8.
The Drupal Console makes use of the Symfony Console and other third party components which allows you to automatically generate most of the code needed for a Drupal 8 module. In addition, Drupal Console helps you interact with your Drupal installation.

+ [Drupal Console website](https://drupalconsole.com/)
+ [Documentation](https://hechoendrupal.gitbooks.io/drupal-console/content/en/index.html)

## Composer

> Dependency management for PHP. Composer helps you declare, manage and install dependencies of PHP projects.

This is a must! Drupal 8 and Magento 2 (and some Magento 1 modules) utilize composer (finally!) for dependency management.

+ [Getting Started](https://getcomposer.org/doc/00-intro.md)
+ [Documentation](https://getcomposer.org/doc/)
+ [Packages](http://packagist.org/)

## N98-Magerun (Magento 1)

> The swiss army knife for Magento developers, sysadmins and devops. The tool provides a huge set of well tested command line commands which save hours of work time. All commands are extendable by a module API. http://magerun.net/

+ Website: https://github.com/netz98/n98-magerun

#### Install with Homebrew

```bash
$ brew install n98-magerun
```

## N98-Magerun2 (Magento 2)

Basically the Swiss Army Knife for Magento 2 developers. Should be compatible with PHP 5.5, 5.6, 7.0

+ Website: https://github.com/netz98/n98-magerun2

#### Install with Homebrew

```bash
$ brew install n98-magerun2
```
