# mpl-switch
`mpl-switch` is a simple installer and version switcher for
[MPL](https://github.com/MPLLang/mpl).

It creates and maintains a `~/.mpl` directory containing local installs
of MPL, organized by commit ID. Note that it is "safe" at any moment to
delete this `~/.mpl` directory; everything in here can be regenerated
automatically.

## Install

Just clone this repo and add the repo directory to your `PATH`.

## Usage

Run the following only once (make sure you put the `export PATH` command
in your `.profile` or `.bashrc` or whatever you use):
```
$ mpl-switch init
$ export PATH="~/.mpl/bin:$PATH"
```

To install a particular version of MPL (this will take a while):
```
$ mpl-switch install <COMMIT>
```

To select a version of MPL to use:
```
$ mpl-switch select <COMMIT>
```

To see which versions are already installed:
```
$ mpl-switch list
```

## Example

Here's an example on my machine.
```
$ mpl-switch init
initialized /usr0/home/swestric/.mpl
make sure this is in your PATH: /usr0/home/swestric/.mpl/bin

$ export PATH="~/.mpl/bin:$PATH"
$ which mpl
/usr0/home/swestric/.mpl/bin/mpl

$ mpl-switch install b6eed2941e81ced341c7aff3731ec25238cd50ce
...
$ mpl-switch install a969232df75dac4ac44c917ea8fed973c0226cd7
...
$ mpl-switch list
installed versions:
  b6eed2941e81ced341c7aff3731ec25238cd50ce
  a969232df75dac4ac44c917ea8fed973c0226cd7

$ mpl-switch select a969232df75dac4ac44c917ea8fed973c0226cd7
$ mpl
MLton [mpl] 20200115.194836-ga969232

$ mpl-switch select b6eed2941e81ced341c7aff3731ec25238cd50ce
$ mpl
MLton [mpl] 20200929.203633-gb6eed29
```
