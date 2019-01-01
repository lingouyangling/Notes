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
os.mkdir(dir name)
```
make new directories with multiple levels
```python
os.makedirs(dir path)
```
remove a dir under the current dir
```python
os.rmdir(dir name)
```
remove dirs with a tree structure
```python
os.removedirs(dir path)
```
rename
```python
os.rename(old name, new name)
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
os.path.split(file path)
```
split a file path to a root and extension
```python
os.path.splitext(file path)
```
check if a path exists
```python
os.path.exists(file path)
```
check if a path is a dir
```python
os.path.isdir(path)
```
check if a path is a file
```python
os.path.isfile(path)
```
