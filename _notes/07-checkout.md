

checkout: Read tree and move HEAD



## Implment

```
def checkout (oid):
    commit = get_commit (oid)
    read_tree (commit.tree)
    data.set_HEAD (oid)
```