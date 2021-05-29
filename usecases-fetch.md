# `fetch` UseCases

## basic usage

```git fetch [<options>] [<repository> [<refspec>...]]```

```git fetch [<options>] <group>```

```git fetch --multiple [<options>] [(<repository> | <group>)...]```

```git fetch --all [<options>]```

## fetch a specific tag from a remote

git fetch ${remote_name} ${tag_name}


## Usage on script
```sh
TARGET_VERSION=1.0.0
REMOTE_NAME=my_remote
if [[ ! -z $(git fetch -q "$REMOTE_NAME" "v$TARGET_VERSION") ]]; then
  echo "!!! couldn't fetch v$TARGET_VERSION from $REMOTE_NAME"
  exit 1
fi
```
