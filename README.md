## Name
gzoo - transparently decompress gzipped files

## Synopsis
    gzoo <COMMAND> [ARG0, ARG1, ...]

## Description
Transparently transforms arguments of command. 
If an argument ends in .gz and it points to a regular file, gzip -cd is invoked in a child process on this file, and the argument is replaced by a special filename (/proc/self/fd/N). 
The command can then read this file and get the decompressed contents.

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

