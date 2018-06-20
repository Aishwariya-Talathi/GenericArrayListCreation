# GenericArrayListCreation

Created my own generic/template MyArrayList<T> in Java. 
MyArrayList mimics more or less exactly, the behavior of Java’s ArrayList. 
•	Did not use Java’s ArrayList or any predefined type or class.
•	a native array ( [ ] ) is used to store the array’s data.

implemented the following operations in MyArrayList:
1.	public MyArrayList(int initialSize)
o creates the array if type T 
o	throws IllegalArgumentException and the initialSize that caused it if less than 0

2.	public MyArrayList()
o	calls MyArrayList(int initalSize) with default size of 10

3.	public int size()
o	the current size of the array

4.	public boolean isEmpty()
o	no elements in the array

5.	public void add(int index, E element)
o	adds element of type E to position index
o	checks for the availability of position index by calling 
o	private void rangeCheckForAdd(int index)
o	on every attempt to add tries to “grow” the array by one
o	note that if an element is added to a non-end position, all elements to the right of the new element are shifted right by one

6.	public boolean add(E e)
o	on every attempt to add tries to “grow” the array by one
o	returns true if successful

7.	public E get(int index)
o	ensures the position exists by calling private void rangeCheck(int index)
o	returns the element at index by calling #8

8.	private E elementData(int index)
o	access the element in the array at position index and return it

9.	private void rangeCheck(int index)
o	if index exceeds size throw IndexOutOfBoundsException

10.	public void grow(int minCap)
o	when asked to grow the array, if minCap is larger than the current length, increase the size by 1.5 times the current size plus 1
o	if that size isn’t larger than minCap, increase the size to minCap

11.	public E set(int index, E element)
o	check the index is in range
o	set aside the current value at position index
o	assign the new element at index
o	return the old element

12.	private void rangeCheckForAdd(int index)
o	the index exceeds the size or is less than 0 throw IndexOutOfBoundsException

13.	private String outOfBoundsMsg(int index)
o	forms and return the error message on out of bounds
o	Index: #  Size: #

14.	public E remove(int index)
o	check the index is in range
o	set aside the current value at position index
o	determine the number of elements to move
o	if > 0 then arraycopy the remaining elements to the right of the removed
o	set the last element position to null
o	decrease size by 1
o	return the set aside element
