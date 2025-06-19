COMP 313/413 Project 2
Ahmad Ahmad

TestList.java and TestIterator.java

	TODO also try with a LinkedList - does it make any difference?

When using a LinkedList instead of an ArrayList, the behavior of the tests does not changed, all tests still passed and the iterator works the same way. But linked lists allow for insertions and removals in the middle of the list.

TestList.java

	testRemoveObject()

		list.remove(5); // what does this method do?

list.remove(5) removes the element at index 5 (the sixth element) from the list.
If the list has fewer than 6 elements, this will throw an IndexOutOfBoundsException
		list.remove(Integer.valueOf(5)); // what does this one do?

list.remove(Integer.valueOf(5)) removes the first occurrence of the value 5 from the list, if it exists.
If the value 5 is not present, the list remains unchanged.



TestIterator.java

	testRemove()

		i.remove(); // what happens if you use list.remove(77)?

If you use list.remove(77) inside the iterator loop, you will get a “ConcurrentModificationException”. This is because modifying the list directly while iterating with an iterator is not allowed. i.remove() safely removes elements during iteration.

TestPerformance.java

	State how many times the tests were executed for each SIZE (10, 100, 1000 and 10000) to get the running time in milliseconds and how the test running times were recorded.
Each test was executed x amount of times for each SIZE. Running times were measured using System.currentTimeMillis() before and after the test code. The difference between end and start times gave the elapsed running time for each test


For list access (getting or setting elements by index), ArrayList is better because it provides constant-time (O(1)) random access. LinkedList requires traversing the list from the beginning or end, resulting in linear-time (O(n)) access.
	listAddRemove - which type of List is better to use, and why?
For add/remove operations (especially in the middle or beginning of the list), LinkedList is better because it can insert or remove elements in constant time (O(1)) (after reaching the position). ArrayList may require shifting many elements, resulting in linear time (O(n)) for these operations. However, for adding/removing at the end, ArrayList is usually faster.
