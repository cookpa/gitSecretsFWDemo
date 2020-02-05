# gitSecretsFWDemo

Test repo for using git-secrets to keep Flywheel API keys safe


# git-secrets

https://github.com/awslabs/git-secrets

I installed with Homebrew, but see the README there for options.


## Repository installation

Each repo that will use git-secrets needs to have the hooks installed:

```
cd /path/to/repo
git secrets --install
```

## Adding secrets

A general regex for Flywheel keys

```
git secrets --add "upenn.flywheel.io:.*"
```

We could make this more specific if there are many false positives.


## Scanning before commit

```
git secrets --scan dummyKey.txt 
```

## Scanning on commit

Try editing `dummyKey.txt` and then adding and committing. You should see an 
error because the file  matches a secret pattern.


