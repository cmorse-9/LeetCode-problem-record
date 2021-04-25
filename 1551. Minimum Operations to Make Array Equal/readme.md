#1551. Minimum Operations to Make Array Equal
arr[i] = (2 * i) + 1
Goal is to make all elements in the array equal to each other, while increment/decrement a number we must decrement/increment another number in the array. 

Example of the array:

n = 3:
Arr [0] [1] [2]
     1   3   5
Target number: 3
Operation: 
  1 5 => 2 4 => 3 3
end of operation
Need to operate 2 times to reach 3 3 3 for the array

n = 4:
Arr [0] [1] [2] [3]
     1   3   5   7
Target number: 4
Operation: 
  3 5 => 4 4
  1 7 => 2 6 => 3 5 => 4 4
end of operation
Need to operate 1+3 = 4 times to reach all 4's in the array

n = 5:
Arr [0] [1] [2] [3] [4]
     1   3   5   7   9
Target number: 5
Operation: 
  3 7 => 4 6 => 5 5
  1 9 => 2 8 => 3 7 => 4 6 => 5 5
end of operation
Need to operate 2+4 = 6 times to reach all 5's in the array

n = 6:
Arr [0] [1] [2] [3] [4] [5]
     1   3   5   7   9  11
Target number: 6
Operation: 
  5 7 => 6 6
  3 9 => 4 8 => 5 7 => 6 6
  1 11 => 2 10 => 3 9 => 4 8 => 5 7 => 6 6
end of operation
Need to operate 1+3+5 = 9 times to reach all 6's in the array

Depending on n is even or odd, this will take sum of all odd or even numbers, the total number of the numbers is from 0 to n/2. 
n is even: 1 + 3 + 5 + 7 + 9...
n is odd: 2 + 4 + 6 + 8 + 10...

```cpp
class Solution {
public:
    int minOperations(int n) {
        // n is odd number
        if(n%2){
            int mid = n / 2;
            int last = n - 1;
            int count = 0;
            int add = 2;
            for(int i = mid; i < last; i++){
                count += add;
                add += 2;
            }
            return count;
        }
        // n is even number
        else{
            int mid = n / 2;
            int last = n - 1;
            int count = 1;
            int add = 1;
            for(int i = mid; i < last; i++){
                add += 2;
                count += add;
                
            }
            return count;
        }
    }
};
```

