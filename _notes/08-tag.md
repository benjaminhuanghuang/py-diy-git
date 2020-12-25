```
$ ugit commit
d8d43b0e3a21df0c845e185d08be8e4028787069

$ ugit tag my-cool-commit d8d43b0e3a21df0c845e185d08be8e4028787069
$ # Make more changes
```

attach a name to an OID. Then we'll be able to refer to the OID by that name.

```
- get_HEAD ()    ->   get_ref ('HEAD')
- set_HEAD (oid) ->   update_ref ('HEAD', oid)
```

## Implement

```
```