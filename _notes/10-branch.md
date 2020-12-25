```
```





```
  branch_parser = commands.add_parser ('branch')
  branch_parser.set_defaults (func=branch)
  branch_parser.add_argument ('name')
  branch_parser.add_argument ('start_point', default='@', type=oid, nargs='?')
```