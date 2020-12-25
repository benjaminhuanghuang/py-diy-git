
```
ugit init
```
Create new .ugit directory



## Implement
cli.py
```
  def init (args):
      data.init ()
```

data.py
```
  import os

  GIT_DIR = '.ugit'

  def init ():
      os.makedirs (GIT_DIR)
```