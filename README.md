# Upgrade Yosemite

A list of known issues when upgrading development machine from osx 10.9 mavericks to osx 10.10 yosemite.

## Before the installation

As part of the installation of Yosemite it will move all the files from /usr/local (Homebrew can easily put over 100k files in /usr/local) and then recover those files back. The recovery process is very slow (few files per second) and can last several hours.

To avoid the slow recovery it is recommended to move all the /usr/local files to a folder in your home directory and move it back once the installation is over.

## Homebrew 

### services

It is required to retap services

```sh
brew tap homebrew/boneyard
```

### postgresql

#### Option 1: Stay with brew

If you installed pg via homebrew you will need to create the following folders to be able to connect to pg

```sh
cd cd /usr/local/var/postgres && mkdir pg_tblspc pg_twophase pg_stat_tmp
```

#### Option 2: Switch to Postgres.app

Alternatively you can use [Postgres.app](http://postgresapp.com/) for psql, and adding the Postgres.app bin directory to $PATH

```sh
export PATH=$PATH:/Applications/Postgres.app/Contents/Versions/9.3/bin
```

## Apps

### Any Jetbrains IDE like PyCharm, PHPStorm, IntelliJ, RubyMine

Will not run on Yosemite unless Java is downgraded to the last stable 1.6 release.

See more here: http://stackoverflow.com/questions/26433495/intellij-not-starting-after-os-x-yosemite-update

### Shiftit

In case you are using [Shiftit](https://github.com/fikovnik/ShiftIt) you need to perform the following actions:

1. Open System preferences -> Security & Privacy
2. Go to Privacy
3. On the Accessibility tab uncheck & check shiftit

Reference: https://github.com/fikovnik/ShiftIt/issues/136

## General

### Pow
[Pow](http://pow.cx/) is broken after the upgrade.

To Fix:

1. Uninstall pow
2. Install pow

```sh
$ curl get.pow.cx/uninstall.sh | sh
$ curl get.pow.cx | sh
```

## License

[![Creative Commons License](http://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)

This work is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).
