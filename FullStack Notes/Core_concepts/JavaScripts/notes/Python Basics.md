---
title: Python Basics
created: '2023-07-04T00:54:57.696Z'
modified: '2023-07-04T01:06:34.858Z'
---

# Python Basics
[Python CheatSheet](https://www.pythoncheatsheet.org/cheatsheet/basics)

# Arrays & Strings Concept
```python
freq = [0] * 26
for i in range(len(s)):
    freq[ord(s[i]) - ord('a')] += 1
    freq[ord(t[i]) - ord('a')] -= 1

```
For each index i, it calculates the ASCII value of the i-th character of s and t using the <mark>ord() function</mark>. By subtracting the ASCII value of 'a' from the calculated value, it maps the characters to the range 0-25 (assuming lowercase English letters only).

```python
hash_s = {}
hash_t = {}
for i in range(len(s)):
    hash_s[s[i]] = 1 + hash_s.get(s[i], 0)
    hash_t[t[i]] = 1 + hash_t.get(t[i], 0)
 return hash_s == hash_t

```
It then updates the frequency count of s[i] and t[i] in hash_s and hash_t, respectively. The hash_s.get(s[i], 0) expression returns the current value associated with the key s[i] in hash_s, or 0 if the key is not present. The +1 increments the frequency count by 1.

``` python
def calculate_sum(self, numbers: List[int]) -> int:

```
In this example, the method name is `calculate_sum`, and it takes two parts in the parameter list: `self` (which represents the instance of the class) and `numbers`, which is a list of integers. The method is expected to return an integer value, as indicated by the `-> int` part of the signature.

The method signature provides a concise overview of the method's input and output requirements and helps understand its purpose and usage without delving into the actual implementation.
```python
my_list = [10, 20, 30, 40, 50]
print(my_list[-1])  # Output: 50
print(my_list[-2])  # Output: 40
#negative indexing
```

``` python
a = " Hello, World! "  
print(a.strip()) # returns "Hello, World!"
```

``` python
The `replace()` method replaces a string with another string:

a = "Hello, World!"  
print(a.replace("H", "J"))
```
```python
quantity = 3  
itemno = 567  
price = 49.95  
myorder = "I want to pay {2} dollars for {0} pieces of item {1}."  
print(myorder.format(quantity, itemno, price))

![](https://storage.googleapis.com/pieces-web-extensions-cdn/pieces.png)Copy and Save![](https://storage.googleapis.com/pieces-web-extensions-cdn/link.png)Share

[Try it Yourself »](https://www.w3schools.com/python/trypython.asp?filename=demo_string_format3)

```

```python
#list used as constructor
thislist = list(("apple", "banana", "cherry")) # note the double round-brackets  
print(thislist)
```

``` python
thislist = ["apple", "banana", "cherry"]  
thistuple = ("kiwi", "orange")  
thislist.extend(thistuple)  
print(thislist)

thislist = ["apple", "banana", "cherry"]  
tropical = ["mango", "pineapple", "papaya"]  
thislist.extend(tropical)  
print(thislist)

thislist = ["apple", "banana", "cherry"]  
thislist.clear()  
print(thislist)

thislist = ["apple", "banana", "cherry"]  
thislist.pop()  
print(thislist)


for x in fruits:
  if "a" in x:
    newlist.append(x)

print(newlist)

#ListComprehension
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]  
  
newlist = [x for x in fruits if "a" in x]  
  
print(newlist)

```
|Method|Description|
|---|---|
|[append()](https://www.w3schools.com/python/ref_list_append.asp)|Adds an element at the end of the list|
|[clear()](https://www.w3schools.com/python/ref_list_clear.asp)|Removes all the elements from the list|
|[copy()](https://www.w3schools.com/python/ref_list_copy.asp)|Returns a copy of the list|
|[count()](https://www.w3schools.com/python/ref_list_count.asp)|Returns the number of elements with the specified value|
|[extend()](https://www.w3schools.com/python/ref_list_extend.asp)|Add the elements of a list (or any iterable), to the end of the current list|
|[index()](https://www.w3schools.com/python/ref_list_index.asp)|Returns the index of the first element with the specified value|
|[insert()](https://www.w3schools.com/python/ref_list_insert.asp)|Adds an element at the specified position|
|[pop()](https://www.w3schools.com/python/ref_list_pop.asp)|Removes the element at the specified position|
|[remove()](https://www.w3schools.com/python/ref_list_remove.asp)|Removes the item with the specified value|
|[reverse()](https://www.w3schools.com/python/ref_list_reverse.asp)|Reverses the order of the list|
|[sort()](https://www.w3schools.com/python/ref_list_sort.asp)|Sorts the list|

