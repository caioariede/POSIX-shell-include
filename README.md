## Summary

POSIX-shell-include is a collection of POSIX-compliant shell snippets that can be embedded in your shell scripts.

## Tool

POSIX-shell-include also provides a CLI tool that can be used to easily embed snippets from the collection.

See the shell script below:
```shell
#!/bin/sh
# File: my-script.sh

# posix-shell-include: shell/command_exists

if shell_command_exists "wget" ; then
	echo "wget is installed"
else
	echo "wget is not installed"
fi
```

Once you run `posix-shell-include -i my-script.sh` it will automatically add the snippet for you:
```shell
#!/bin/sh
# File: my-script.sh

# posix-shell-include: shell/command_exists@0c32ea53f91a898e117e445f3c240479fe7af78b
shell_command_exists() {
	command -v "$1" 1>/dev/null
}

if shell_command_exists "wget" ; then
	echo "wget is installed"
else
	echo "wget is not installed"
fi
```

## Install

```shell
sh -c 'curl -fsSLo $1 https://raw.githubusercontent.com/caioariede/POSIX-shell-include/HEAD/posix-shell-include && chmod +x $1' -- /usr/local/bin/posix-shell-include
```
