# Learning Goal 2: Time Complexity

1. What is the time complexity of the following code in big-o notation. Briefly explain your answer.

```
int sum = 0;
for(int i=0; i<10; i++) {
  for(int j=0; j<5; j++) {
    sum = sum + j;
  }
}
```

Answer:


Explanation: 





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
Answer:



3. What is the Big-O complexity for the following algorithm for determining who stole the cookie from the cookie jar:

Ask the first person if they stole the cookie; if they say it couldn't be them, you ask the second person if they stole the cookie; etc, for each person in the room.

Answer:
