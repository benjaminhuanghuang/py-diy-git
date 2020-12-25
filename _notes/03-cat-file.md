
```
  $ ugit cat-file <hashid>
```

This command is the "opposite" of hash-object: it can print an object by its OID.

## Implement
```
  def cat_file (args):
    sys.stdout.flush ()
    sys.stdout.buffer.write (data.get_object (args.object))

  # reads the file at .ugit/objects/{OID}
  def get_object (oid):
    with open (f'{GIT_DIR}/objects/{oid}', 'rb') as f:
        return f.read ()
```