# proxyenv

This program is designed to be used like proxychains, that is

`proxyenv <any program> <any arguments for the program>`

This program used to be a simple bash function, firsted introduced
at [A shell function to set environemt for any single command (Title has been translated)](https://blog.leafee98.com/posts/%E4%B8%BA%E5%8D%95%E4%B8%80%E5%91%BD%E4%BB%A4%E8%AE%BE%E7%BD%AE%E4%BB%A3%E7%90%86%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F%E7%9A%84%E7%BB%88%E7%AB%AF%E5%87%BD%E6%95%B0/).

It works most of the time, but when using other command wrappers like `sudo proxyenv cmd`,
the shell function will not work anymore, because in the context of sudo, the function
proxyenv is inaccessible.

So I make it as an bash script, which still accessible inside any other program wrappers,
that's this program.

## Usage

```
proxyenv <any program> <any arguments>
```

## Configuration

If environemt `PROXYENV_CONFPATH` is set, the program will use the path indicted by it to
read the proxy actually to be used. Otherwise `/etc/proxyenv.conf` will be used.

The configuration file (default `/etc/proxyenv.conf`) will be sourced when proxyenv run,
so take care no let this file's permission to open, 755 is suggested.

For entry detail of configuration file, see [proxyenv.conf](/proxyenv.conf) in this repository.

## Misc

### Install on Archlinux

Since I add a PKGBUILD at the root of repository, you can use the following command
to build and install this program on Archlinux.

```
makepkg
pacman -U <generated package>
```
