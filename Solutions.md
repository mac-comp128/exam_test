# Solutions

The following are the solutions to the practice problems. Do not look at them until you have tried each problem on your own!

## LG01 Arrays

1. Write the Java code that creates and initializes an integer array named
    myIntArray with the following values: 10, 20, 30, 40.
    
```
    int[] myIntArray = new int[]{10, 20, 30, 40};
```

2. Write the code for the following method that returns the maximum value found in the input array.

```
public static double arrayMax(double[] data) {
    int n = data.length;
    double currentMax = data[0];
    for (int j=1; j < n; j++) {
        if (data[j] > currentMax) {
             currentMax = data[j];
        }
    }
    return currentMax;
}
```

3. **Optional bonus question related to sorting** Assume the input array in the previous question is an array of Strings. How would your code need to change to return the string that comes last in alphabetical ordering?

```
Other than simple things like changing the currentMax variable to a string, the main change would be to the conditional. Instead of using a > symbol the condition would be replaced with:

if (data[j].compareTo(currentMax) > 0)
```


## LG02 Time Complexity

1. What is the time complexity of the following code in big-o notation. Briefly explain your answer.

```
int sum = 0;
for(int i=0; i<10; i++) {
  for(int j=0; j<5; j++) {
    sum = sum + j;
  }
}
```

Answer: O(n^2)


Explanation:  Assume that n = 10. The outer loop runs n times. The inner loop runs n/2 times. The line of code that sums can be done in constant time. Since the loops are nested the runtime multiplies together to run n^2/2 times, but we drop the 1/2 multiplier to simplify.





2. What is the Big-O runtime of the following code?

```
/∗∗ Returns true if there is no element common to all three arrays. ∗/
public static boolean noCommonElements(int[ ] groupA, int[ ] groupB, int[ ] groupC) {
    for (int a : groupA) {
        for (int b : groupB) {
             for (int c : groupC) {
                       if ((a == b) && (b == c))
                            return false;
              }
           }
     }
  return true;
}
```
Answer: O(n^3)



3. What is the Big-O complexity for the following algorithm for determining who stole the cookie from the cookie jar:

Ask the first person if they stole the cookie; if they say it couldn't be them, you ask the second person if they stole the cookie; etc, for each person in the room.

Answer: O(n)


## LG03 Stacks

1. Write a method called removeNegatives  that takes a stack of Integer objects as a parameter and returns the stack with all negative numbers removed. For example, if the original stack contained 30, -15, 20, -25 (top of stack), the new stack would look like 30, 20 (top of stack).

```
public Deque<Integer> removeNegatives(Deque<Integer> inStack) {
    Deque<Integer> tempStack = new ArrayDeque<>(inStack.size());
    while (!inStack.isEmpty()) {
        Integer next = inStack.pop();
        if (next >= 0) {
            tempStack.push();
        }
    }
    while (!tempStack.isEmpty()) {
        inStack.push(tempStack.pop);
    }
    return inStack;
}
```

2. Which implementation of a stack (array-based or linked-node based) would be most efficient in terms of time complexity to use for the inStack parameter variable in the above question. Briefly justify your answer using big-o notation. If both implementations would be the same, state why.

Answer: 

Both implementations would be identical in terms of big-o time complexity. The push and  pop methods are both O(1) for both implementations because in the array-based you just need to add the item to the top index and increment top and in the linked node-based you just need to reassign a constant number of links. The isEmpty method is also O(1) for both because you store either the top or a count variable to keep track of the number of elements. As a result each while loop runs in O(n) time so the total runtime of the method for both is O(n).
