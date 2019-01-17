use the os module   
```python
import os
```
get the current working directory
```python
os.getcwd()
```
change the current working directory
```python
os.chdir(dir path)
```
list files and folders in the current directory
```python
os.listdir()
```
make a new directory under the current directory
```python
os.mkdir(dirname)
```
make new directories with multiple levels
```python
os.makedirs(dirpath)
```
remove a dir under the current dir
```python
os.rmdir(dirname)
```
remove dirs with a tree structure
```python
os.removedirs(dirpath)
```
rename
```python
os.rename(oldname, newname)
```
get information of a file
```python
os.stat(filename)
```
get the size (bytes) of a file
```python
os.stat(filename).st_size
```
get the last modification time of a file
```python
os.stat(filename).st_mtime
```
see the entire directory tree   
the os.walk() creates a generator with 3-value tuples
```python
for dirpath, dirnames, filenames in os.walk(path):
    print('Current Path:', dirpath)
    print('Directories:', dirnames)
    print('Files:', filenames)
    print()
```
get enviroment variables
```python
os.environ
```
concat path
```python
os.path.join(path1, path2)
```
get the basename of a file
```python
os.path.basename(filename)
```
split a file path to a dir and a file name
```python
os.path.split(filepath)
```
split a file path to a root and extension
```python
os.path.splitext(filepath)
```
check if a path exists
```python
os.path.exists(filepath)
```
check if a path is a dir
```python
os.path.isdir(path)
```
check if a path is a file
```python
os.path.isfile(path)
```
