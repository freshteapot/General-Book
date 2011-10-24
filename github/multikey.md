#Setting ssh to use multikeys

Firstly, github.com themseleves [explain](http://help.github.com/multiple-ssh-keys/ "Setting up multiple keys in ssh to work with github") how to do it here. However I only found that afterwards.


```
ssh-keygen -f ~/.ssh/moveable -t rsa -C 'Moveable'
```

Then alter:
```
~/.ssh/config
```

Setting up git to work with other keys other than the default.

"http://dracoblue.net/dev/custom-identity-file-idrsapub-with-git-client/193/"  - This got me almost there.

This helped me fill in the missing bit "Host". In hindsight, a school boy error for not trying it with ".com" on the end.



## Searched for:

setup git to use identify file for ssh
ssh specify key

## Links
* http://help.github.com/multiple-ssh-keys/
* http://dracoblue.net/dev/custom-identity-file-idrsapub-with-git-client/193/















# Running vmware headless on a mac.

## Read the help file.
```
    cd /Library/Application Support/VMware Fusion
    ./vmrun --help
```

## Example format for starting.
```
    ./vmrun -T ws start PATH_TO_FILE nogui
```

###Notes
* Added this to my "[General-Book](https://github.com/freshteapot/General-Book)".