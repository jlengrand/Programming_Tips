# OpenCV

Memos and Tips about the OpenCV library.

## In C/C++:

### Placing a pointer to the beginning of pixel in an image:

Can be used to naviguate through pixels easily (and more efficiently than some openCV functions).

```C
char *pImage = iplImage->ImageData
```


### Short review of the IplImage structure:

What’s really needed to work with an Image
```C
* IplImage struct {
    depth # Number of channels (gray level, color, . . .)
    sizeX
    sizeY
    * ImageData } #Pixels of the image
    ...}
```


### Simple tips for Image Processing optimization in C:

An image is stored in a memory a a long line (n*m size)

Always go __trough the buffer way__, and not the opposite!
```C
for (i in nb_lines):
    for (j in nb_cols):
        //do stuff
    }
}
```

and

```C
for (j in nb_cols):
    for (i in nb_lines):
        //do stuff
    }
}
```

are different ! **The second one is 10% faster than the other !**

##In Python :

Error on compiling OpenCV with Python bindings:

If you get this error when trying to compile OpenCV in Linux
```bash
Could NOT find PythonLibs (missing: PYTHON_INCLUDE_DIRS) in cmake
```

Simply try installing python-dev packages.
```bash
$ sudo apt-get install python-dev
```

It should solve the problem.