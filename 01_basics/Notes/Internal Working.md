# Internal Working of Python

- Python internally doesn't keep any empty references.
- Python treats strings and number slightly different from other data types.
- ref_count : reference count
- Datatypes are allocated in memory not to variables in python ,variable refer that memory which holds the datatype.
- Garbage collection does not work immediately on the numbers and strings as soon as its empty.
-  'is' keyword in python checks memory reference of two objects , where == checks values of two objects
- whenever you perfrom slicing [:] or any other operation , it creates a copy of that refernce.
