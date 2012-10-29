# PYTHON

## Get variable name as a string:

```Python
blah = 1
blah_name = [ k for k , v in locals (). iteritems () if v is blah ][ 0 ]
```

 __**WARNING :** Not very clever however, as variables in Python may have more that one name ! Use with caution!__

## Replace a part of a table [Numpy]:

```Python
small_BW=where((L[temp[ptr-1]]==ptr),1,0)
a=BW[posi_0:posi_1,posi_2:posi_3]
a[:,:]=small_BW.copy()
```

## Reshape table without size information:

Put -1 as second argument, the info will automatically be processed.

```Python
array.reshape(3,-1)
```

## Concatenate 2 tables [Numpy]:

```Python
c=numpy.concatenate((a,b),axis=0)
```

## Cast data in table to int:

```Python
Ndarray.astype(int)
```

## Write in the end of a file :

Use add mode :

```Python
file.open(file_name, 'a')
```

## Test if variable exists:

```Python
try:
    print variable
except NameError:
    print "Error!"
```

## Check if variable is one of several choices:

```Python
if a in [b, c,d]:
    blabla
```

## Multi instanciation in Python:

```Python
a = b = c = 1+1
```

__**WARNING:** Those three variables are the same object!__

## Print function name :

```Python
import sys

def tutut():
    """
    Dum function displaying its name!
    """
    print sys._getframe().f_code.co_name

if __name__ == '__main__':
    tutut()
```

And here is the result

```Bash
$ python tutut.py
tutut
```