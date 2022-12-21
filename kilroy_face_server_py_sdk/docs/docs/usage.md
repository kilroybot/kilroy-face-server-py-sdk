# Usage

You can use this package to easily create a face server
that complies with the **kilroy** face API.

The easiest way to do this is to create a class that inherits from `Face` class
and implement all the necessary methods.
All methods are either simple coroutines or async generators.

Here is an example:

```python
from pathlib import Path
from kilroy_face_server_py_sdk import Face, FaceService, FaceServer

class MyFace(Face):
    ... # Implement all necessary methods here

face = await MyFace.build()
service = FaceService(face, Path("path/to/state/directory"))
server = FaceServer(service)

await server.run(host="0.0.0.0", port=10000)
```
