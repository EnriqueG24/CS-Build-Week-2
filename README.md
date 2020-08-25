# CS Build Week 2: Interview Prep

This is a general repo that you can fork for holding any artifacts you
might need to submit during the week. Feel free to make subdirectories
here as necessary.

For all details about the week, [check out the page in
TrainingKit](https://learn.lambdaschool.com/cs/sprint/reco0t22NdXmr8VyL).

---

## Code Challenge - Arrays

Given an array, **A** , of **N** integers, print each element in reverse order as a single line of space-separated integers.

```swift
// Sample Input
1 4 3 2

// Output
2 3 4 1
```

##### My Solution
```Swift
func reverseArray(a: [Int]) -> [Int] {
    // So we can obtain the value a single time instead of once per iteration
    let total = a.count - 1
    // The value that we're going to return
    var reversedNumbers = [Int]()
    // For loop to iterate from 0 to the amount of elements through our array
    for  arrayIndex in 0...total {
        // Append the elements from our input array into our reversedNumber array
        reversedNumbers.append(a[total - arrayIndex])
    }
    // Return our array of reversed integers
    return reversedNumbers
}
```
---

## Code Challenge - Contains Duplicates

Given an array of integers, find if the array contains any duplicates.

Your function should return true if any value appears at least twice in the array, and it should return false if every element is distinct.

```swift
/*
Input: [1,2,3,1]
Output: True

Input: [1,2,3,4]
Output: False
*/
```

#### My Solution

```swift
class Solution {
    func containsDuplicate(_ nums: [Int]) -> Bool {
        // We'll use a set since Sets can't contain duplicate values. We'll compare the numbers of elements
        if nums.count != Set(nums).count {
            // Return true if the numbers of elements dont' match (there are duplicate values) 
            return true
        } else { 
            // Otherwise return false
            return false
        }
    }
}
```
---

## Code Challenge - Two Sum

Given an array of integers, return **indices** of the two numbers such that they add up to a specific target. You may assume that each input would have **exactly** one solution, and you may no tuse the *same* element twice.

```swift
/* 
Given nums = [2, 7, 11, 15], target = 9

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1]
*/
```

#### My Solution

```swift
class Solution {
    func twoSum(_ nums: [Int], _ target: Int) -> [Int] {
        // This dictionary will store the numbers in the input as keys and their indices as values
        var dict = [Int: Int]()
        
        // We'll use enumerated to return a sequence of pairs
        for (i, num) in nums.enumerated() { 
            // We'll subtract num from the target to find the other number we need, that way they add up to the target
            if let lastIndex = dict[target - num] { 
                // If the dictionary knows what index the other number is at, we return that index, and i
                return [lastIndex, i]
            }
            // If we haven't seen that number before, we record i into the dictionary under the key num
            dict[num] = i
        }
        return [0, 0]
    }
}
```
---
## Code Challenge - Implement Queue using Stacks

Implement the following operations of a queue using stacks.
 * push(x) -- Push element x to the back of queue
 * pop() -- Removes the element from in front of queue
 * peek() -- Get the front element
 * empty() -- Return whether the queue is empty


#### My Solution

```python
class MyQueue(object):

    def __init__(self):
    # Initialize your data structure
        self.items = []
        
    def push(self, x):
    # Push element x to the back of queue
        self.items.insert(0, x)
    
    def pop(self):
    # Removes the element from in front of queue and returns that element
        return self.items.pop()
    
    def peek(self):
    # Get the front element
        return self.items[len(self.items)-1]
    
    def empty(self):
    # Returns whether the queue is empty
        return self.items == []
```
