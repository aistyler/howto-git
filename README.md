# howto-git

Git usage Alpha to Omega

## Git Internal References

- references(refs): alias of raw SHA-1 value (something like 'ec9103f573377420afabafc09a714aa406b3493d')

```sh
# refs in local repo
$ find .git/refs -type f
.git/refs/heads/branch-1
.git/refs/heads/main
.git/refs/tags/v1.0.1
.git/refs/remotes/origin/branch-1
.git/refs/remotes/origin/HEAD
.git/refs/remotes/origin/main
```

- HEAD: ref of last commit

```sh
$ cat .git/HEAD
# print 
$ git symbolic-ref HEAD
```

- FETCH_HEAD: branch of last git-fetch

```sh
$ cat .git/FETCH_HEAD
```

## Revisions

- ~(tilde): ${rev}~${n}, e.g. master~1
- ^(caret): ${rev}^${n}, e.g. master^1

```txt
       A      <= HEAD
     /   \
    B     C
 /  |  \ /
D   E   F
| \     | \
G  H    I  J

A =      = A^0
B = A^   = A^1     = A~1
C = A^2
D = A^^  = A^1^1   = A~2
E = B^2  = A^^2
F = B^3  = A^^3
G = A^^^ = A^1^1^1 = A~3
H = D^2  = B^^2    = A^^^2  = A~2^2
I = F^   = B^3^    = A^^3^
J = F^2  = B^3^2   = A^^3^2
```
