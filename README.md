# cs61a-lab-8--midterm-solved
**TO GET THIS SOLUTION VISIT:** [CS61A Lab 8- Midterm Solved](https://www.ankitcodinghub.com/product/cs61a-lab-8-midterm-review-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;119674&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS61A  Lab 8- Midterm Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
Starter Files

Download lab08.zip. Inside the archive, you will find starter files for the questions in this lab, along with a copy of the Ok autograder.

Topics

Consult this section if you need a refresher on the material for this lab. It’s okay to skip directly to the questions and refer back here should you get stuck.

Iterators

An iterable is any object that can be iterated through, or gone through one element at a time. One construct that we’ve used to iterate through an iterable is a for loop:

py for elem in iterable: # do something

for loops work on any object that is iterable. We previously described it as working with any sequence — all sequences are iterable, but there are other objects that are also iterable! We define an iterable as an object on which calling the built-in iter function returns an iterator. An iterator is another type of object that allows us to iterate through an iterable by keeping track of which element is next in the sequence.

To illustrate this, consider the following block of code, which does the exact same thing as the for statement above:

py iterator = iter(iterable) try: while True: elem = next(iterator) # do something except StopIteration: pass

Here’s a breakdown of what’s happening:

First, the built-in iter function is called on the iterable to create a corresponding iterator.

To get the next element in the sequence, the built-in next function is called on this iterator.

When next is called but there are no elements left in the iterator, a StopIteration error is raised. In the for loop construct, this exception is caught and execution can continue.

Calling iter on an iterable multiple times returns a new iterator each time with distinct states (otherwise, you’d never be able to iterate through a iterable more than once). You can also call iter on the iterator itself, which will just return the same iterator without changing its state. However, note that you cannot call next directly on an iterable.

Let’s see the iter and next functions in action with an iterable we’re already familiar with — a list. “`py

lst = [1, 2, 3, 4] next(lst) # Calling next on an iterable TypeError: ‘list’ object is not an iterator list_iter = iter(lst) # Creates an iterator for the list list_iter next(list_iter) # Calling next on an iterator 1 next(list_iter) # Calling next on the same iterator 2 next(iter(list_iter)) # Calling iter on an iterator returns itself 3 list_iter2 = iter(lst) next(list_iter2) # Second iterator has new state 1 next(list_iter) # First iterator is unaffected by second iterator 4 next(list_iter) # No elements left! StopIteration lst # Original iterable is unaffected [1, 2, 3, 4] “`

Since you can call iter on iterators, this tells us that that they are also iterables! Note that while all iterators are iterables, the converse is not true that is, not all iterables are iterators. You can use iterators wherever you can use iterables, but note that since iterators keep their state, they’re only good to iterate through an iterable once: “`py

list_iter = iter([4, 3, 2, 1]) for e in list_iter: … print(e) 4 3 2 1 for e in list_iter: … print(e) “`

Analogy: An iterable is like a book (one can flip through the pages) and an iterator for a book would be a bookmark (saves the position and can locate the next page). Calling iter on a book gives you a new bookmark independent of other bookmarks, but calling iter on a bookmark gives you the bookmark itself, without changing its position at all. Calling next on the bookmark moves it to the next page, but does not change the pages in the book. Calling next on the book wouldn’t make sense semantically. We can also have multiple bookmarks, all independent of each other.

Iterable Uses

“`py

for x in range(2, 6): … print(x) … 2 3 4 5 “`

Ranges are useful for many things, including performing some operations for a particular number of iterations or iterating through the indices of a list.

There are also some built-in functions that take in iterables and return useful results:

map(f, iterable) – Creates an iterator over f(x) for x in iterable. In some cases, computing a list of the values in this iterable will give us the same result as [func(x) for x in iterable]. However, it’s important to keep in mind that iterators can potentially have infinite values because they are evaluated lazily, while lists cannot have infinite elements.

filter(f, iterable) – Creates an iterator over x for each x in iterable if f(x)

zip(iterables*) – Creates an iterator over co-indexed tuples with elements from each of the iterables reversed(iterable) – Creates an iterator over all the elements in the input iterable in reverse order list(iterable) – Creates a list containing all the elements in the input iterable tuple(iterable) – Creates a tuple containing all the elements in the input iterable sorted(iterable) – Creates a sorted list containing all the elements in the input iterable

reduce(f, iterable) – Must be imported with functools. Apply function of two arguments f cumulatively to the items of iterable, from left to right, so as to reduce the sequence to a single value.

Generators

We can create our own custom iterators by writing a generator function, which returns a special type of iterator called a generator. Generator functions have yield statements within the body of the function instead of return statements. Calling a generator function will return a generator object and will not execute the body of the function.

For example, let’s consider the following generator function:

py def countdown(n): print(“Beginning countdown!”) while n &gt;= 0: yield n n -= 1 print(“Blastoff!”)

Calling countdown(k) will return a generator object that counts down from k to 0. Since generators are iterators, we can call iter on the resulting object, which will simply return the same object. Note that the body is not executed at this point; nothing is printed and no numbers are outputted. “`py

c = countdown(5) c c is iter(c) True “`

So how is the counting done? Again, since generators are iterators, we call next on them to get the next element! The first time next is called, execution begins at the first line of the function body and continues until the yield statement is reached. The result of evaluating the expression in the yield statement is returned. The following interactive session continues from the one above. “`py

next(c) Beginning countdown! 5 “`

Unlike functions we’ve seen before in this course, generator functions can remember their state. On any consecutive calls to next, execution picks up from the line after the yield statement that was previously executed. Like the first call to next, execution will continue until the next yield statement is reached. Note that because of this, Beginning countdown! doesn’t get printed again. “`py

next(c) 4 next(c) 3 “`

The next 3 calls to next will continue to yield consecutive descending integers until 0. On the following call, a StopIteration error will be raised because there are no more values to yield (i.e. the end of the function body was reached before hitting a yield statement). “`py

next(c) 2 next(c) 1 next(c) 0 next(c) Blastoff! StopIteration “`

Separate calls to countdown will create distinct generator objects with their own state. Usually, generators shouldn’t restart. If you’d like to reset the sequence, create another generator object by calling the generator function again. “`py

c1, c2 = countdown(5), countdown(5) c1 is c2 False next(c1) 5 next(c2) 5 “`

Here is a summary of the above:

A generator function has a yield statement and returns a generator object.

Calling the iter function on a generator object returns the same object without modifying its current state.

The body of a generator function is not evaluated until next is called on a resulting generator object. Calling the next function on a generator object computes and returns the next object in its sequence. If the sequence is exhausted, StopIteration is raised.

A generator “remembers” its state for the next next call. Therefore, the first next call works like this:

1. Enter the function and run until the line with yield.

2. Return the value in the yield statement, but remember the state of the function for future next calls.

And subsequent next calls work like this:

1. Re-enter the function, start at the line after the yield statement that was previously executed, and run until the next yield statement.

2. Return the value in the yield statement, but remember the state of the function for future next calls.

Calling a generator function returns a brand new generator object (like calling iter on an iterable object).

A generator should not restart unless it’s defined that way. To start over from the first element in a generator, just call the generator function again to create a new generator.

Another useful tool for generators is the yield from statement. yield from will yield all values from an iterator or iterable. “`py

def gen_list(lst): … yield from lst … g = gen_list([1, 2, 3, 4]) next(g) 1 next(g) 2 next(g) 3 next(g) 4 next(g) StopIteration “`

Required Questions

Iterators &amp; Generators

Q1: Repeated

Implement repeated, which takes in an iterator t and returns the first value in t that appears k times in a row.

Note: You can assume that the iterator t will have a value that appears at least k times in a row. If you are receiving a StopIteration, your repeated function is likely not identifying the correct value.

Your implementation should iterate through the items in a way such that if the same iterator is passed into repeated twice, it should continue in the second call at the point it left off in the first. An example of this behavior is in the doctests.

“`py def repeated(t, k): “””Return the first value in iterator T that appears K times in a row. Iterate through the items such that if the same iterator is passed into the function twice, it continues in the second call at the point it left off in the first.

&gt;&gt;&gt; s = iter([10, 9, 10, 9, 9, 10, 8, 8, 8, 7])

&gt;&gt;&gt; repeated(s, 2)

9

&gt;&gt;&gt; s2 = iter([10, 9, 10, 9, 9, 10, 8, 8, 8, 7])

&gt;&gt;&gt; repeated(s2, 3)

8

&gt;&gt;&gt; s = iter([3, 2, 2, 2, 1, 2, 1, 4, 4, 5, 5, 5])

&gt;&gt;&gt; repeated(s, 3)

2

&gt;&gt;&gt; repeated(s, 3)

5

&gt;&gt;&gt; s2 = iter([4, 1, 6, 6, 7, 7, 8, 8, 2, 2, 2, 5])

&gt;&gt;&gt; repeated(s2, 3)

2 “””

assert k &gt; 1

“*** YOUR CODE HERE ***”

“`

Use Ok to test your code:

py python3 ok -q repeated

Q2: Merge

You will probably find it helpful to use the two-argument version of the built-in next function: next(incr, v) is the same as next(incr), except that instead of raising StopIteration when incr runs out of elements, it returns v.

See the doctest for examples of behavior.

&gt;&gt;&gt; m = merge([0, 2, 4, 6, 8, 10, 12, 14], [0, 3, 6, 9, 12, 15])

&gt;&gt;&gt; type(m)

&lt;class ‘generator’&gt;

&gt;&gt;&gt; list(m)

[0, 2, 3, 4, 6, 8, 9, 10, 12, 14, 15] &gt;&gt;&gt; def big(n):

… k = 0

… while True: yield k; k += n

&gt;&gt;&gt; m = merge(big(2), big(3))

&gt;&gt;&gt; [next(m) for _ in range(11)]

[0, 2, 3, 4, 6, 8, 9, 10, 12, 14, 15]

“””

iter_a, iter_b = iter(incr_a), iter(incr_b)

next_a, next_b = next(iter_a, None), next(iter_b, None) “*** YOUR CODE HERE ***”

“`

Use Ok to test your code:

py python3 ok -q merge

Linked Lists &amp; Trees

Q3: Deep Linked List Length

A linked list that contains one or more linked lists as elements is called a deep linked list. Write a function deep_len that takes in a (possibly deep) linked list and returns the deep length of that linked list. The deep length of a linked list is the total number of non-link elements in the list, as well as the total number of elements contained in all contained lists. See the function’s doctests for examples of the deep length of linked lists.

Hint: Use isinstance to check if something is an instance of an object.

“`py def deep_len(lnk): “”” Returns the deep length of a possibly deep linked list.

&gt;&gt;&gt; deep_len(Link(1, Link(2, Link(3))))

3

&gt;&gt;&gt; deep_len(Link(Link(1, Link(2)), Link(3, Link(4))))

4

&gt;&gt;&gt; levels = Link(Link(Link(1, Link(2)),

Link(3)), Link(Link(4), Link(5)))

&gt;&gt;&gt; print(levels)

&lt;&lt;&lt;1 2&gt; 3&gt; &lt;4&gt; 5&gt;

&gt;&gt;&gt; deep_len(levels)

5 “”” if ______________:

return 0 elif ______________: return 1 else: return _________________________

“`

Use Ok to test your code:

py python3 ok -q deep_len Q4: Add Leaves

Implement add_d_leaves, a function that takes in a Tree instance t and a number v.

We define the depth of a node in t to be the number of edges from the root to that node. The depth of root is therefore 0.

For each node in the tree, you should add d leaves to it, where d is the depth of the node. Every added leaf should have a label of v. If the node at this depth has existing branches, you should add these leaves to the end of that list of branches.

For example, you should be adding 1 leaf with label v to each node at depth 1, 2 leaves to each node at depth 2, and so on.

Here is an example of a tree t(shown on the left) and the result after add_d_leaves is applied with v as 5.

Try drawing out the second doctest to visualize how the function is mutating t3.

Hint: Use a helper function to keep track of the depth!

“`py def add_d_leaves(t, v): “””Add d leaves containing v to each node at every depth d.

&gt;&gt;&gt; t_one_to_four = Tree(1, [Tree(2), Tree(3, [Tree(4)])])

&gt;&gt;&gt; print(t_one_to_four)

1

2

3

4

&gt;&gt;&gt; add_d_leaves(t_one_to_four, 5)

&gt;&gt;&gt; print(t_one_to_four)

1

2

5

3

4

5

5

5

&gt;&gt;&gt; t1 = Tree(1, [Tree(3)])

&gt;&gt;&gt; add_d_leaves(t1, 4)

&gt;&gt;&gt; t1

Tree(1, [Tree(3, [Tree(4)])])

&gt;&gt;&gt; t2 = Tree(2, [Tree(5), Tree(6)])

&gt;&gt;&gt; t3 = Tree(3, [t1, Tree(0), t2])

&gt;&gt;&gt; print(t3)

3

1

3

4

0

2

5

6

&gt;&gt;&gt; add_d_leaves(t3, 10)

&gt;&gt;&gt; print(t3)

3

1

3

4

10

10

10

10

10

10

0

10

2

5

10

10

6

10

10

10

“””

“*** YOUR CODE HERE ***”

“`

Use Ok to test your code:

py python3 ok -q add_d_leaves

Efficiency

Q5: Efficiency Practice

Choose the term that fills in the blank for the functions defined below: &lt;function&gt; runs in ____ time in the length of its input.

Constant

Logarithmic

Linear

Quadratic

Exponential

None of these

Assume that len runs in constant time and all runs in linear time in the length of its input. Selecting an element of a list by its index requires constant time. Constructing a range requires constant time.

“`py def count_partitions(n, m): “””Counts the number of partitions of a positive integer n, using parts up to size m.””” if n == 0: return 1 elif n &lt; 0: return 0 elif m == 0: return 0 else: with_m = count_partitions(n-m, m) without_m = count_partitions(n, m-1) return with_m + without_m def is_palindrome(s): “””Return whether a list of numbers s is a palindrome.””” return all([s[i] == s[len(s) – i – 1] for i in range(len(s))])

def binary_search(lst, n): “””Takes in a sorted list lst and returns the index where integer n is contained in lst. Returns -1 if n does not exist in lst.””” low = 0 high = len(lst) while low &lt;= high: middle = (low + high) // 2 if lst[middle] == n: return middle elif n &lt; lst[middle]: high = middle – 1 else: low = middle + 1 return -1 “`

Use Ok to test your understanding:

py python3 ok -q efficiency_practice -u

Submit

Make sure to submit this assignment by running:

py python3 ok –submit

Extra Practice

Recursion and Tree Recursion

Q6: Subsequences

A subsequence of a sequence S is a subset of elements from S, in the same order they appear in S. Consider the list [1, 2, 3]. Here are a few of it’s subsequences [], [1, 3], [2], and [1, 2, 3].

Write a function that takes in a list and returns all possible subsequences of that list. The subsequences should be returned as a list of lists, where each nested list is a subsequence of the original input.

In order to accomplish this, you might first want to write a function insert_into_all that takes an item and a list of lists, adds the item to the beginning of each nested list, and returns the resulting list.

“`py def insert_into_all(item, nested_list): “””Return a new list consisting of all the lists in nested_list, but with item added to the front of each. You can assume that nested_list is a list of lists.

&gt;&gt;&gt; nl = [[], [1, 2], [3]]

&gt;&gt;&gt; insert_into_all(0, nl)

[[0], [0, 1, 2], [0, 3]]

“””

“*** YOUR CODE HERE ***”

def subseqs(s): “””Return a nested list (a list of lists) of all subsequences of S. The subsequences can appear in any order. You can assume S is a list.

&gt;&gt;&gt; seqs = subseqs([1, 2, 3])

&gt;&gt;&gt; sorted(seqs)

[[], [1], [1, 2], [1, 2, 3], [1, 3], [2], [2, 3], [3]]

&gt;&gt;&gt; subseqs([])

[[]] “”” if ________________: ________________ else:

________________

________________

“`

Use Ok to test your code:

py python3 ok -q subseqs

Q7: Non-Decreasing Subsequences

Just like the last question, we want to write a function that takes a list and returns a list of lists, where each individual list is a subsequence of the original input.

This time we have another condition: we only want the subsequences for which consecutive elements are nondecreasing. For example, [1, 3, 2] is a subsequence of [1, 3, 2, 4], but since 2 &lt; 3, this subsequence would not be included in our result.

“`py def non_decrease_subseqs(s): “””Assuming that S is a list, return a nested list of all subsequences of S (a list of lists) for which the elements of the subsequence are strictly nondecreasing. The subsequences can appear in any order.

&gt;&gt;&gt; seqs = non_decrease_subseqs([1, 3, 2])

&gt;&gt;&gt; sorted(seqs)

[[], [1], [1, 2], [1, 3], [2], [3]]

&gt;&gt;&gt; non_decrease_subseqs([])

[[]]

&gt;&gt;&gt; seqs2 = non_decrease_subseqs([1, 1, 2])

&gt;&gt;&gt; sorted(seqs2)

[[], [1], [1], [1, 1], [1, 1, 2], [1, 2], [1, 2], [2]]

“”” def subseq_helper(s, prev): if not s: return ____________________ elif s[0] &lt; prev: return ____________________ else: a = ______________________ b = ______________________

return insert_into_all(________, ______________) + ________________ return subseq_helper(____, ____)

“`

Use Ok to test your code:

py python3 ok -q non_decrease_subseqs

Mutable Lists

Q8: Shuffle

Define a function shuffle that takes a sequence with an even number of elements (cards) and creates a new list that interleaves the elements of the first half with the elements of the second half.

To interleave two sequences s0 and s1 is to create a new sequence such that the new sequence contains (in this order) the first element of s0, the first element of s1, the second element of s0, the second element of s1, and so on. If the two lists are not the same length, then the leftover elements of the longer list should still appear at the end.

Note: If you’re running into an issue where the special heart / diamond / spades / clubs symbols are erroring in the doctests, feel free to copy paste the below doctests into your file as these don’t use the special characters and should not give an “illegal multibyte sequence” error.

“`py def card(n): “””Return the playing card numeral as a string for a positive n &lt;= 13.””” assert type(n) == int and n &gt; 0 and n &lt;= 13, “Bad card n” specials = {1: ‘A’, 11: ‘J’, 12: ‘Q’, 13: ‘K’} return specials.get(n, str(n)) def shuffle(cards): “””Return a shuffled list that interleaves the two halves of cards.

&gt;&gt;&gt; shuffle(range(6))

[0, 3, 1, 4, 2, 5]

&gt;&gt;&gt; suits = [‘H’, ‘D’, ‘S’, ‘C’]

&gt;&gt;&gt; cards = [card(n) + suit for n in range(1,14) for suit in suits]

&gt;&gt;&gt; cards[:12]

[‘AH’, ‘AD’, ‘AS’, ‘AC’, ‘2H’, ‘2D’, ‘2S’, ‘2C’, ‘3H’, ‘3D’, ‘3S’, ‘3C’]

&gt;&gt;&gt; cards[26:30]

[‘7S’, ‘7C’, ‘8H’, ‘8D’]

&gt;&gt;&gt; shuffle(cards)[:12]

[‘AH’, ‘7S’, ‘AD’, ‘7C’, ‘AS’, ‘8H’, ‘AC’, ‘8D’, ‘2H’, ‘8S’, ‘2D’, ‘8C’]

&gt;&gt;&gt; shuffle(shuffle(cards))[:12]

[‘AH’, ‘4D’, ‘7S’, ’10C’, ‘AD’, ‘4S’, ‘7C’, ‘JH’, ‘AS’, ‘4C’, ‘8H’, ‘JD’]

&gt;&gt;&gt; cards[:12] # Should not be changed

[‘AH’, ‘AD’, ‘AS’, ‘AC’, ‘2H’, ‘2D’, ‘2S’, ‘2C’, ‘3H’, ‘3D’, ‘3S’, ‘3C’]

“””

assert len(cards) % 2 == 0, ‘len(cards) must be even’ half = _______________ shuffled = [] for i in _____________: _________________ _________________ return shuffled

“`

Use Ok to test your code:

py python3 ok -q shuffle

Generators &amp; Iterators

Q9: Pairs (generator)

Write a generator function pairs that takes a list and yields all the possible pairs of elements from that list.

py def pairs(lst): “”” &gt;&gt;&gt; type(pairs([3, 4, 5])) &lt;class ‘generator’&gt; &gt;&gt;&gt; for x, y in pairs([3, 4, 5]): … print(x, y) … 3 3 3 4 3 5 4 3 4 4 4 5 5 3 5 4 5 5 “”” “*** YOUR CODE HERE ***”

Use Ok to test your code:

py python3 ok -q pairs Q10: Pairs (iterator)

Now write an iterator that does the same thing. You are only allowed to use a linear amount of space – so computing a list of all of the possible pairs is not a valid answer. Notice how much harder it is – this is why generators are useful.

“`py class PairsIterator: “”” &gt;&gt;&gt; for x, y in PairsIterator([3, 4, 5]): … print(x, y) … 3 3 3 4 3 5 4 3 4 4 4 5 5 3 5 4 5 5 “”” def init(self, lst): ”

YOUR CODE HERE ”

def __next__(self):

“*** YOUR CODE HERE ***”

def __iter__(self):

“*** YOUR CODE HERE ***”

“`

Use Ok to test your code:

py python3 ok -q PairsIterator

Trees

Q11: Long Paths

Implement long_paths, which returns a list of all paths in a tree with length at least n. A path in a tree is a linked list of node values that starts with the root and ends at a leaf. Each subsequent element must be from a child of the previous value’s node. The length of a path is the number of edges in the path (i.e. one less than the number of nodes in the path). Paths are listed in order from left to right. See the doctests for some examples.

“`py def long_paths(tree, n): “””Return a list of all paths in tree with length at least n.

&gt;&gt;&gt; t = Tree(3, [Tree(4), Tree(4), Tree(5)])

&gt;&gt;&gt; left = Tree(1, [Tree(2), t])

&gt;&gt;&gt; mid = Tree(6, [Tree(7, [Tree(8)]), Tree(9)])

&gt;&gt;&gt; right = Tree(11, [Tree(12, [Tree(13, [Tree(14)])])]) &gt;&gt;&gt; whole = Tree(0, [left, Tree(13), mid, right])

&gt;&gt;&gt; for path in long_paths(whole, 2): … print(path) …

&lt;0 1 2&gt;

&lt;0 1 3 4&gt;

&lt;0 1 3 4&gt;

&lt;0 1 3 5&gt;

&lt;0 6 7 8&gt;

&lt;0 6 9&gt;

&lt;0 11 12 13 14&gt;

&gt;&gt;&gt; for path in long_paths(whole, 3): … print(path) …

&lt;0 1 3 4&gt;

&lt;0 1 3 4&gt;

&lt;0 1 3 5&gt;

&lt;0 6 7 8&gt;

&lt;0 11 12 13 14&gt;

&gt;&gt;&gt; long_paths(whole, 4)

[Link(0, Link(11, Link(12, Link(13, Link(14)))))]

“””

“*** YOUR CODE HERE ***”

“`

Use Ok to test your code:

py python3 ok -q long_paths

Linked Lists

Q12: Flip Two

Write a recursive function flip_two that takes as input a linked list s and mutates s so that every pair of values in the linked list is flipped.

“`py def flip_two(s): “”” &gt;&gt;&gt; one_lnk = Link(1) &gt;&gt;&gt; flip_two(one_lnk) &gt;&gt;&gt; one_lnk Link(1) &gt;&gt;&gt; lnk = Link(1, Link(2, Link(3, Link(4, Link(5))))) &gt;&gt;&gt; flip_two(lnk) &gt;&gt;&gt; lnk Link(2, Link(1, Link(4, Link(3, Link(5))))) “”” ” YOUR CODE HERE ”

# For an extra challenge, try writing out an iterative approach as well below! “*** YOUR CODE HERE ***”

“`

Use Ok to test your code:

py python3 ok -q flip_two
