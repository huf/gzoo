## Name
gzoo - transparently decompress gzipped files

## Synopsis
    gzoo [OPTIONS] <COMMAND> [ARG0, ARG1, ...]

## Description
Allows a command to read from gzipped files, even if it cannot itself gunzip said files.
All arguments ending in ".gz" and representing regular files will be replaced with special filenames (/proc/self/fd/N). Reading from these files will return the decompressed content of the argument they replace.
The command is then executed with the new argument list and may do what it will.

## Options
`--cat`
> The program is now a cat. Your move.

`--kecske` (or `--goat`)
> What does a goat say in english?

`--version`
> ...

`--help` or `-h`
> some

`-v` or `-V` or `-x` or `-X` or `-i` or `-I`
> In case you forget your basic roman numerals.

## Example
    # you type:
    $ gzoo cat a b.gz
	# cat will see something like this:
	cat a /proc/self/fd/3
	# and will print the same thing as if you'd done:
	$ zcat a b.gz
	# but this will work for any command.

## License
Same as Perl.

