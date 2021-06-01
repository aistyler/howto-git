# `update-index` UseCases

Register file contents in the working tree to the index

## basic usage

```git update-index [--add] [--remove | --force-remove] [--[no-]assume-unchanged] [<file>]```

## keep a file in a git-repo, but don't track changes

```sh
# ignore any changes
git update-index --assume-unchanged <file>

# track the changes again
git update-index --no-assume-unchanged <file>
```
