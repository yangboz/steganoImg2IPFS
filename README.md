# steganoImg2IPFS
verify chatgpt's  proof-of-concept  of stegano image to IPFS

## chatgpt 
Q:
proof-of-concept  of stegano image to IPFS
A:
Steganography is the practice of hiding information within other, seemingly harmless information. One way to implement a proof-of-concept for a steganographic image on IPFS (InterPlanetary File System) would be to use a library or tool that allows you to embed a message or file within an image file and then upload the resulting image to IPFS.


Here is an example of how you might go about creating a proof-of-concept for a steganographic image on IPFS using the Python programming language and the PySteg library:

Install the PySteg library by running pip install pysteg in your terminal.
Import the necessary modules in your Python script:
```
from pysteg.lsb import LSB
from pysteg.common import *

```
Load the image file that you want to use as the cover image for your steganographic image. You can do this using the imread function from the skimage library:
```
from skimage.io import imread
cover_image = imread("cover_image.png")

```

### 4.Encode the message or file that you want to hide within the cover image using the encode function from the LSB class:
```
lsb = LSB(cover_image)
encoded_image = lsb.encode("secret message")

```
### 5.Save the encoded image to a file using the imsave function from the skimage library:

```
from skimage.io import imsave
imsave("encoded_image.png", encoded_image)

```

### 6.Upload the encoded image to IPFS using the ipfsapi library:

```
import ipfsapi
api = ipfsapi.connect()
result = api.add("encoded_image.png")
print(result)

```

This should give you the hash of the encoded image on IPFS, which you can use to retrieve the image and decode the hidden message or file. Note that this is just one way to implement a proof-of-concept for a steganographic image on IPFS, and there are many other tools and libraries that you can use to achieve the same result.

##TODO
using fastapi to wrap this PoC as an API for SAAS. 
