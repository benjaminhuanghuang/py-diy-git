
```
write-tree
```
In Git's lingo a "tree" means a directory.

This command will take the current working directory and store it to the object database.

If hash-object was for storing an individual file, then write-tree is for storing a whole directory.

the content of tree
```
91a7b14a584645c7b995100223e65f8a5a33b707 cats.txt
fa958e0dd2203e9ad56853a3f51e5945dad317a4 dogs.txt
```

## Implement
cli.py
```
def write_tree (args):
    base.write_tree ()


def read_tree (args):
    base.read_tree (args.tree)
```    

base.py
```
  import os

  from . import data

  def write_tree (directory='.'):
      with os.scandir (directory) as it:
          for entry in it:
              full = f'{directory}/{entry.name}'
              if entry.is_file (follow_symlinks=False):
                  # TODO write the file to object store
                  print (full)
              elif entry.is_dir (follow_symlinks=False):
                  write_tree (full)

      # TODO actually create the tree object


  def read_tree (tree_oid):
    for path, oid in get_tree (tree_oid, base_path='./').items ():
        os.makedirs (os.path.dirname (path), exist_ok=True)
        with open (path, 'wb') as f:
            f.write (data.get_object (oid))

```

