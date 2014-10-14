iostest-PhotoLibraryImport
==========================

Test helper that imports Photo Library from .zip

Why
---

Testing PhotoLibrary-related codes are pretty hard. If we can import photos and albums from .zip file, it might comes easier.

How
---

Make `library.zip` with following structure.

```
library.zip
|- xxx.jpg
|- xxx.jpg
|- ...
|
|- Some Album Name
|   |
|   |- xxx.jpg
|   |- xxx.jpg
|   |..
|
|- Hawaii
    |- xxx.jpg
```

The point is

1. Photos placed on root directory goes to Camera Roll.
2. Directories placed on root directory becomes an album which named the directory's name.
3. Photos placed on some directory goes to an album which named the directory's name.

And put it on project and bundle it.

Then

```
[KITestPhotoLibraryImport importFromZipNamed:@"library.zip"];
```

While it will not be done immediately, it works asynchronously for easier syntax.
