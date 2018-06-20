# GenericArrayListCreation

Created my own generic/template MyArrayList<T> in Java. 
MyArrayList mimics more or less exactly, the behavior of Java’s ArrayList. 
•	Did not use Java’s ArrayList or any predefined type or class.
•	a native array ( [ ] ) is used to store the array’s data.

implemented the following operations in MyArrayList:
1.	public MyArrayList(int initialSize)
• creates the array if type T 
•	throws IllegalArgumentException and the initialSize that caused it if less than 0

2.	public MyArrayList()
•	calls MyArrayList(int initalSize) with default size of 10

3.	public int size()
•	the current size of the array

4.	public boolean isEmpty()
•	no elements in the array

5.	public void add(int index, E element)
• adds element of type E to position index
•	checks for the availability of position index by calling 
•	private void rangeCheckForAdd(int index)
•	on every attempt to add tries to “grow” the array by one
•	note that if an element is added to a non-end position, all elements to the right of the new element are shifted right by one

6.	public boolean add(E e)
•	on every attempt to add tries to “grow” the array by one
•	returns true if successful

7.	public E get(int index)
•	ensures the position exists by calling private void rangeCheck(int index)
•	returns the element at index by calling #8

8.	private E elementData(int index)
•	access the element in the array at position index and return it

9.	private void rangeCheck(int index)
•	if index exceeds size throw IndexOutOfBoundsException

10.	public void grow(int minCap)
•	when asked to grow the array, if minCap is larger than the current length, increase the size by 1.5 times the current size plus 1
•	if that size isn’t larger than minCap, increase the size to minCap

11.	public E set(int index, E element)
•	check the index is in range
•	set aside the current value at position index
•	assign the new element at index
•	return the old element

12.	private void rangeCheckForAdd(int index)
•	the index exceeds the size or is less than 0 throw IndexOutOfBoundsException

13.	private String outOfBoundsMsg(int index)
•	forms and return the error message on out of bounds
•	Index: #  Size: #

14.	public E remove(int index)
•	check the index is in range
•	set aside the current value at position index
•	determine the number of elements to move
•	if > 0 then arraycopy the remaining elements to the right of the removed
•	set the last element position to null
•	decrease size by 1
•	return the set aside element
