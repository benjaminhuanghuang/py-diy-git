
```
ugit hash-object <file>
```
This command will take a file and store it in .ugit directory for later retrieval.

So the flow of the command hash-object is:
- Get the path of the file to store.
- Read the file.
- Hash the content of the file using SHA-1.
- Store the file under ".ugit/objects/{the SHA-1 hash}".

## Implement

sha1sum sample
```
  $ echo -n this is cool | sha1sum
  60f51187e76a9de0ff3df31f051bde04da2da891

  $ echo -n this is cooler | sha1sum
  f3c953b792f9ab39d1be0bdab7ab5f8350593004
```


```
def hash_object (args):
  with open (args.file, 'rb') as f:
    print (data.hash_object (f.read ()))


def hash_object (data):
    oid = hashlib.sha1 (data).hexdigest ()
    with open (f'{GIT_DIR}/objects/{oid}', 'wb') as out:
        out.write (data)
    return oid    
```