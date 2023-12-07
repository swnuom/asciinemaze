# asciinemaze
Creates "human-made-like" asciinema ascii-casts out of the provided regular text file as if we would type it!

# extensions
The input file can use the following special characters:
1. *±*: Line that contains prompt.
2. *§*: Output of commands.
3. *&*: Clears screen (if it is the only character in the line)
4. *~*: Wait a few seconds (if it is the only character in the line)

# useful commands

The following command adds the special character `§` in all lines that do not start with `±` (display at once all non prompt lines).

```console
sed -i '/^±/!s/^/§/' input.txt
```

You can also do it for lines that do not have on character only (i.e., skip "clear screen" or "wait a few second" characters).

```console
sed -i '/^±/!s/^.\\{2,\\}/§/' input.txt
```

The following command adds the special character `±` at the beginning of all lines that contain character `$` (there is a prompt).

```console
sed -i '/\$/s/^/±/' input.txt
```

# Demo

[![asciicast](https://asciinema.org/a/YAO5k8H8GBiTFNIdG0oIb6izV.svg)](https://asciinema.org/a/YAO5k8H8GBiTFNIdG0oIb6izV)
