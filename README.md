# CS Build Week 2: Interview Prep

This is a general repo that you can fork for holding any artifacts you
might need to submit during the week. Feel free to make subdirectories
here as necessary.

For all details about the week, [check out the page in
TrainingKit](https://learn.lambdaschool.com/cs/sprint/reco0t22NdXmr8VyL).

---

## Code Challenge Problems

Arrays - DS

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
