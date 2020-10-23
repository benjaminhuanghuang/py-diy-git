

This command is the "opposite" of hash-object: it can print an object by its OID. Its implementation just reads the file at .ugit/objects/{OID}.

The names hash-object and cat-file aren't the clearest of names, but they are the names that Git uses so we'll stick to them for consistency.


Usage
```
$ cd /tmp/new
$ ugit init
Initialized empty ugit repository in /tmp/new/.ugit
$ echo some file > bla
$ ugit hash-object bla
0e08b5e8c10abc3e455b75286ba4a1fbd56e18a5
$ ugit cat-file 0e08b5e8c10abc3e455b75286ba4a1fbd56e18a5
some file
```