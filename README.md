## please.sh
*This is a very early alpha version*

Put your scripts in the please-command folder and create two functions: the run function and the help function:
- `[ name of file ]_run() { }`
- `[ name of file ]_help { }`

Link the please script in your $PATH

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