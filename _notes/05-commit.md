```
ugit commit 
```
command that will accept a commit message, snapshot the current directory using ugit write-tree and save the resulting object.

A commit will just be a text file stored in the object database with the type of 'commit'.

```
tree 50bed982245cd21e2798f179e0b032904398485b
parent bd0de093f1a0f90f54913d694a11cccf450bd990

This is the commit message!
```

## Implement
cli.py
```
  def commit (args):
    print (base.commit (args.message))
```

base.py
```
  def commit (message):
      commit = f'tree {write_tree ()}\n'
      HEAD = data.get_HEAD ()
      if HEAD:
          commit += f'parent {HEAD}\n'

      commit += '\n'
      commit += f'{message}\n'

      oid = data.hash_object (commit.encode (), 'commit')
      # record the OID of the last commit that we created
      data.set_HEAD (oid)

      return oid

  def set_HEAD (oid):
    with open (f'{GIT_DIR}/HEAD', 'w') as f:
        f.write (oid)


  def get_HEAD ():
    if os.path.isfile (f'{GIT_DIR}/HEAD'):
        with open (f'{GIT_DIR}/HEAD') as f:
            return f.read ().strip ()      
```