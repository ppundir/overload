# overload
Function overloading
overloading is a module that provides function and method dispatching based on the types and number of arguments.

Installation

1. Clone the git repository
2. python setup.py install

Usage:
Argument to decorator must define number and type of arguments ( defined in python by type(arg) or arg.__class__)

>>> a= 12
>>> a.__class__
<type 'int'>
>>>
>>> a= 34.34
>>> a.__class__
<type 'float'>
>>>
>>> a = [12,67]
>>> a.__class__
<type 'list'>
>>>
>>>
>>> a= {}
>>> a.__class__
<type 'dict'>
>>>
>>> a= ()
>>> a.__class__
<type 'tuple'>
>>>
>>> a= 'test'
>>> a.__class__
<type 'str'>

Thus arguments to decorator would be like list,tuple,dict,int,float and str.

Example:

from overloading import overload

@overload(int, int)
def area(length, breadth):
    calc = length * breadth
    print calc

@overload(int)
def area(size):
    calc =  size * size
    print calc

@overload(list)
def area(mylist):
	retlist = []
	for elem in mylist:
		retlist.append(elem * elem)
	print retlist

@overload(list,list)
def area(mylist1,mylist2):
	retlist = []
	for i in range(0,len(mylist1)):
		retlist.append(mylist1[i] * mylist2[i])
	print retlist


area(3)   # will print 9
area(4,5) # will print 20
area([1,2,3]) # will print [1, 4, 9]
area([1,2,3],[4,5,6]) # will print [4, 10, 18]

Documentation

The concept is explained in my blog at https://medium.com/@hitechpundir/function-overloading-in-python-94a8b10d1e08




