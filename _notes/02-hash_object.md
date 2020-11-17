## ugit hash-object
```
$ echo some file > bla
$ ugit hash-object bla
```

This command will take a file and store it in our .ugit directory for later retrieval.

So the flow of the command hash-object is:
- Get the path of the file to store.
- Read the file.
- Hash the content of the file using SHA-1.
- Store the file under ".ugit/objects/{the SHA-1 hash}".


