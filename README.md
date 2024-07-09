# What is it?
This is a small repository that delegates Python's read and write (and file creation!) functions to speed them up, but is slightly different from Python's approach to opening files. Written exclusively in rust!

## Required to run
- Python 3
- Maturin (`pip install maturin`)
- Rust compiler
For Windows:
- Visual Studio 2017 and higher

## Compilation
```shell
cd binder
maturin build --release
CD..
pip install ./binder_r/target/wheels/binder.*.whl
```

## Usage
```python
from binder import reader, writer, creator

filename = 'test.txt'
creator(filename) # Create a file
writer(filename, 'Hello world!\nThat\'s me!') # Write to file
reader(filename)
#Output:
# Hello world!
# That's me!
```
<blockquote> By the way, it is not necessary to create a file before writing; if you call writer without first creating it, it will automatically create the file! </blockquote>