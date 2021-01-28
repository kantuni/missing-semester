# Lecture 1
https://missing.csail.mit.edu/2020/course-shell/

## Exercises

> 2\. Create a new directory called `missing` under `/tmp`.

```bash
cd /tmp
mkdir missing
```

> 3\. Look up the `touch` program. The `man` program is your friend.

```bash
man touch
```

The `touch` utility sets the modification and access times of files.  If any file does not exist, it is created with default permissions.

> 4\. Use `touch` to create a new file called `semester` in `missing`.

```bash
cd missing
touch semester
```

> 5\. Write the following into that file, one line at a time:

```bash
#!/bin/sh  
curl --head --silent https://missing.csail.mit.edu
```

> The first line might be tricky to get working. It’s helpful to know that `#` starts a comment in Bash, and `!` has a special meaning even within double-quoted (`"`) strings. Bash treats single-quoted strings (`'`) differently: they will do the trick in this case. See the Bash [quoting](https://www.gnu.org/software/bash/manual/html_node/Quoting.html) manual page for more information.

```bash
echo '#!/bin/sh' > semester
echo "curl --head --silent https://missing.csail.mit.edu" >> semester
```
From the [bash documentation](https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#Double-Quotes):
> Enclosing characters in double quotes preserves the literal value of all characters within the quotes, with the exception of `$`, `` ` ``, `\`, and, when history expansion is enabled, `!`.

**NOTE:** Use single quotes if there is a `!` inside of a string.

> 6\. Try to execute the file, i.e. type the path to the script (`./semester`) into your shell and press enter. Understand why it doesn’t work by consulting the output of `ls` (hint: look at the permission bits of the file).

```bash
./semester
# permission denied: ./semester

ls -l
# -rw-r--r--  1 henrikh  wheel  61 Jan 28 12:53 semester
```
The `x` (execute) bits are missing.

> 7\. Run the command by explicitly starting the `sh` interpreter, and giving it the file `semester` as the first argument, i.e. `sh semester`. Why does this work, while `./semester` didn’t?

- with `sh`, you're running a program that will interpret the lines in your script just as if you would have typed them on the interactive prompt of the terminal. The file doesn't need to be executable.
- with `./` you're making a shortcut assuming that the script is just right here in the current directory you're sitting in AND it will be executable.

Source: https://askubuntu.com/a/22948

> 8\. Look up the `chmod` program (e.g. use `man chmod`).

The `chmod` utility modifies the file mode bits of the listed files as specified by the mode operand. It may also be used to modify the Access Control Lists (ACLs) associated with the listed files.
