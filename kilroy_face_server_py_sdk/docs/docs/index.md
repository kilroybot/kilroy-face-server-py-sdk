# kilroy-face-server-py-sdk

SDK for kilroy face servers in Python 🧰

## Installing

Using `pip`:

```sh
pip install kilroy-face-server-py-sdk
```

## Usage

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
