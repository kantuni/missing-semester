# Lecture 1

## Exercises

**2. Create a new directory called `missing` under `/tmp`.**

```bash
cd /tmp
mkdir missing
```

**3. Look up the `touch` program. The `man` program is your friend.**

```bash
man touch
```

**4. Use `touch` to create a new file called `semester` in `missing`.**

```bash
cd missing
touch semester
```

**5. Write the following into that file, one line at a time:**

```bash
#!/bin/sh  
curl --head --silent https://missing.csail.mit.edu
```

```bash
echo '#!/bin/sh' > semester
echo "curl --head --silent https://missing.csail.mit.edu" >> semester
```

Double quotes won't work in the first example, because of the `!`.  
From the [bash documentation](https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#Double-Quotes):
> Enclosing characters in double quotes preserves the literal value of all characters within the quotes, with the exception of `$`, `` ` ``, `\`, and, when history expansion is enabled, `!`.
