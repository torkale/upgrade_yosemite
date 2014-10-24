# Upgrade Yosemite

A list of known issues when upgrading development machine from osx 10.9 mavericks to osx 10.10 yosemite.

It is recommended to perform the update overnight as it requires several hours.

## Homebrew 

### services

It is required to retap services

```sh
brew tap homebrew/boneyard
```

### postgresql

If you installed pg via homebrew you will need to create the following folders to be able to connect to pg

```sh
cd cd /usr/local/var/postgres && mkdir pg_tblspc pg_twophase pg_stat_tmp
```

Alternatively you can use [Postgres.app](http://postgresapp.com/) for psql, and adding the Postgres.app bin directory to $PATH

```sh
export PATH=$PATH:/Applications/Postgres.app/Contents/Versions/9.3/bin
```

## Apps

### Shiftit

In case you are using Shiftit you need to perform the following actions:

1. Open System preferences -> Security & Privacy
2. Go to Privacy
3. On the Accessibility tab uncheck & check shiftit

Reference: https://github.com/fikovnik/ShiftIt/issues/136

## License

[![Creative Commons License](http://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)

This work is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).
