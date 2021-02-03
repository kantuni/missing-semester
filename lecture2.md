# Lecture 1

https://missing.csail.mit.edu/2020/shell-tools/

## Exercises

> 2\. Read `man ls` and write an `ls` command that lists files in the following manner:
> 
> - Includes all files, including hidden files
> - Sizes are listed in human readable format (e.g. 454M instead of 454279954)
> - Files are ordered by recency
> - Output is colorized
> 
> A sample output would look like this:

```
 -rw-r--r--   1 user group 1.1M Jan 14 09:53 baz
 drwxr-xr-x   5 user group  160 Jan 14 09:53 .
 -rw-r--r--   1 user group  514 Jan 14 06:42 bar
 -rw-r--r--   1 user group 106M Jan 13 12:12 foo
 drwx------+ 47 user group 1.5K Jan 12 18:08 ..
```

```bash
ls -ahltG
```

- `-a` - Include directory entries whose names begin with a dot (`.`).
- `-h` - When used with the `-l` option, use unit suffixes: Byte, Kilobyte, Megabyte, Gigabyte,
Terabyte and Petabyte in order to reduce the number of digits to three or less using base 2 for sizes.
- `-l` - List in long format.
- `-t` - Sort by time modified (most recently modified first) before sorting 
the operands by lexicographical order.
- `-G` - Enable colorized output.  This option is equivalent to defining CLICOLOR in the environment.

<br />
