# please.sh
*This is a very early alpha version*

## Description
Please.sh is a polite way to run and organize your Bash scripts.

Please was inspired by this talk:
       Shell Ninja: Mastering the Art of Shell Scripting | Roland Huß
       https://www.youtube.com/watch?v=1mt2-LbKuvY

And uses code based on this project:
    https://github.com/syndesisio/syndesis/tree/master/tools/bin

```
>$ please [ script name ] [ options ]
```

## Installation
Just link the please script into $PATH.

## Usage
Put your scripts in the please-commands folder and create two functions: the run function and the help function:
- `[ name of file ]_run() { }`
- `[ name of file ]_help() { }`
- There's no need to change permissions on your script

Please.sh handles flags and options for you with hasFlag() and readOpt()

 - hasFlag(): Returns 'true' if the flag is passed in on the command line
 
```bash
if $(hasFlag -h); then
    echo "this is a helpful message"
fi
```

- readOpt(): Return the value of the option passed in on the command line

```bash
pathOfFile=$(readOpt --file)

if [[ -e  $pathOfFile ]]; then
    echo "file existis"
fi
```

- hasInternet(): Returns true if ping returns a packet from 1.1.1.1

```bash
if $(hasInternet); then
    git pull
fi
```