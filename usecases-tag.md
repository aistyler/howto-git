# `tag` UseCases

## basic usage

```txt
usage: git tag [-a | -s | -u <key-id>] [-f] [-m <msg> | -F <file>]
		<tagname> [<head>]
   or: git tag -d <tagname>...
   or: git tag -l [-n[<num>]] [--contains <commit>] [--no-contains <commit>] [--points-at <object>]
		[--format=<format>] [--merged <commit>] [--no-merged <commit>] [<pattern>...]
   or: git tag -v [--format=<format>] <tagname>...
```

## create a "lite-tag" from the current commit on local

```sh
git tag v1.0.0
```

## push tags on local to the remote repo

```sh
git push --tags
```

## rename tag

```sh
# 1. create ${new} tag from ${old} tag
git tag ${new} ${old}
# 2. delete ${old} tag
git tag -d ${old}
# 3. delete ${old} tag from remote
git push origin :${old}
# 4. push ${new} tag
git push --tags

# 4. remove the deleted tag on the cloned repository
git pull --prune --tags
```