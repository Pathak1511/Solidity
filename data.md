## Find the average of three numbers

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract AverageCalculator {

    function calculateAverage(uint256 num1, uint256 num2, uint256 num3) public pure returns (uint256) {
        // Calculate the sum of the three numbers
        uint256 sum = num1 + num2 + num3;

        // Calculate the average by dividing the sum by the number of elements (3)
        uint256 average = sum / 3;

        // Return the calculated average
        return average;
    }
}
```

Explanation of the code:

1. The contract named `AverageCalculator` contains a function `calculateAverage` that takes three unsigned integers (`num1`, `num2`, and `num3`) as input parameters.

2. Inside the function:

   - The `sum` variable is calculated by adding the three input numbers (`num1`, `num2`, and `num3`).
   - The `average` variable is then calculated by dividing the `sum` by the number of elements (3).

3. Finally, the function returns the calculated average.

## calculates the sum of the digits of a given number:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract DigitSumCalculator {

    function calculateDigitSum(uint256 number) public pure returns (uint256) {
        // Ensure the number is non-negative
        require(number >= 0, "Input number must be non-negative");

        // Initialize a variable to store the sum of digits
        uint256 sum = 0;

        // Loop through each digit of the number
        while (number != 0) {
            // Extract the last digit of the number
            uint256 digit = number % 10;

            // Add the digit to the sum
            sum += digit;

            // Remove the last digit from the number
            number = number / 10;
        }

        // Return the calculated sum of digits
        return sum;
    }
}
```

Explanation of the code:

1. The contract named `DigitSumCalculator` contains a function `calculateDigitSum` that takes an unsigned integer `number` as an input parameter.

2. Inside the function:

   - A `require` statement is used to ensure that the input number is non-negative. If the input is negative, the function will revert with an error message.

   - The variable `sum` is initialized to store the sum of digits.

   - The function enters a `while` loop that continues until the `number` becomes 0.

   - Inside the loop:
     - The last digit of the number is extracted using the modulo operator (`number % 10`).
     - The extracted digit is added to the `sum`.
     - The last digit is removed from the number by dividing it by 10 (`number = number / 10`).

3. After the loop completes, the function returns the calculated sum of digits.

This contract demonstrates a simple approach to calculate the sum of digits in a number. This approach assumes the input number is an unsigned integer.

## isPalindrome

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract PalindromeChecker {
    // Function to check if a number is a palindrome
    function isPalindrome(uint256 number) public pure returns (bool) {
        // Ensure the number is non-negative
        require(number >= 0, "Input number must be non-negative");

        // Initialize variables
        uint256 num = number;
        uint256 reversed = 0;

        // Reverse the number
        while (num > 0) {
            reversed = reversed * 10 + num % 10;
            num /= 10;
        }

        // Check if the reversed number is equal to the original number
        return number == reversed;
    }
}
```

Explanation:

1. **Modifiers and Pragmas:**

   - `// SPDX-License-Identifier: MIT`: This is a SPDX license identifier specifying the license under which the contract is released.
   - `pragma solidity ^0.8.0;`: This pragma statement specifies that the contract is compatible with Solidity version 0.8.0 and higher.

2. **Contract Definition:**

   - `contract PalindromeChecker { ... }`: This defines a Solidity contract named `PalindromeChecker`.

3. **Function to Check Palindrome:**

   - `function isPalindrome(uint256 number) public pure returns (bool) { ... }`: This function takes an unsigned integer `number` as input, and it returns a boolean indicating whether the number is a palindrome or not. The function is marked as `pure` because it doesn't modify the state of the contract.

4. **Input Validation:**

   - `require(number >= 0, "Input number must be non-negative");`: This line ensures that the input number is non-negative. If the condition is not met, the function will revert with the specified error message.

5. **Variable Initialization:**

   - `uint256 num = number;`: This line initializes a variable `num` to store the original number for later comparison.
   - `uint256 reversed = 0;`: This line initializes a variable `reversed` to store the reversed number. It starts with a value of 0.

6. **Reverse the Number:**

   - The `while` loop iterates through each digit of the original number:
     - `reversed = reversed * 10 + num % 10;`: This line reverses the digits of the number. It multiplies the current reversed number by 10 and adds the last digit of the original number.
     - `num /= 10;`: This line removes the last digit from the original number.

7. **Check Palindrome:**
   - `return number == reversed;`: This line checks if the reversed number is equal to the original number. If they are equal, the function returns `true`, indicating that the number is a palindrome; otherwise, it returns `false`.

This single function incorporates all the logic to check if a number is a palindrome without the need for a separate helper function.

## Reversing a number in Solidity

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract NumberReverser {
    // Function to reverse a number
    function reverseNumber(uint256 num) public pure returns (uint256) {
        // Ensure the number is non-negative
        require(num >= 0, "Input number must be non-negative");

        // Initialize a variable to store the reversed number
        uint256 reversed = 0;

        // Reverse the number
        while (num > 0) {
            reversed = reversed * 10 + num % 10;  // Reverse the digits
            num /= 10;                             // Remove the last digit
        }

        // Return the reversed number
        return reversed;
    }
}
```

Explanation:

1. **Modifiers and Pragmas:**

   - `// SPDX-License-Identifier: MIT`: This is a SPDX license identifier specifying the license under which the contract is released.
   - `pragma solidity ^0.8.0;`: This pragma statement specifies that the contract is compatible with Solidity version 0.8.0 and higher.

2. **Contract Definition:**

   - `contract NumberReverser { ... }`: This defines a Solidity contract named `NumberReverser`.

3. **Function to Reverse a Number:**

   - `function reverseNumber(uint256 num) public pure returns (uint256) { ... }`: This function takes an unsigned integer `num` as input, and it returns the reversed version of the number. The function is marked as `pure` because it doesn't modify the state of the contract.

4. **Input Validation:**

   - `require(num >= 0, "Input number must be non-negative");`: This line ensures that the input number is non-negative. If the condition is not met, the function will revert with the specified error message.

5. **Variable Initialization:**

   - `uint256 reversed = 0;`: This line initializes a variable `reversed` to store the reversed number. It starts with a value of 0.

6. **Reverse the Number:**

   - The `while` loop iterates through each digit of the original number:
     - `reversed = reversed * 10 + num % 10;`: This line reverses the digits of the number. It multiplies the current reversed number by 10 and adds the last digit of the original number.
     - `num /= 10;`: This line removes the last digit from the original number.

7. **Return Reversed Number:**
   - `return reversed;`: This line returns the final reversed number.

## number is prime:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract PrimeChecker {
    // Function to check if a number is prime (brute-force approach)
    function isPrime(uint256 number) public pure returns (bool) {
        // Ensure the number is greater than 1
        require(number > 1, "Input number must be greater than 1");

        // Check for divisors using a brute-force approach
        for (uint256 i = 2; i < number; i++) {
            if (number % i == 0) {
                // If the number has a divisor other than 1 and itself, it's not prime
                return false;
            }
        }

        // If no divisors were found, the number is prime
        return true;
    }
}
```

Explanation:

1. **Modifiers and Pragmas:**

   - `// SPDX-License-Identifier: MIT`: This is a SPDX license identifier specifying the license under which the contract is released.
   - `pragma solidity ^0.8.0;`: This pragma statement specifies that the contract is compatible with Solidity version 0.8.0 and higher.

2. **Contract Definition:**

   - `contract PrimeChecker { ... }`: This defines a Solidity contract named `PrimeChecker`.

3. **Function to Check Prime (Brute-Force):**

   - `function isPrime(uint256 number) public pure returns (bool) { ... }`: This function takes an unsigned integer `number` as input, and it returns a boolean indicating whether the number is prime or not. The function is marked as `pure` because it doesn't modify the state of the contract.

4. **Input Validation:**

   - `require(number > 1, "Input number must be greater than 1");`: This line ensures that the input number is greater than 1. Numbers less than or equal to 1 are not prime by definition.

5. **Check for Divisors (Brute-Force):**

   - The `for` loop checks for divisors from 2 up to `number - 1`.
   - `if (number % i == 0) { ... }`: This condition checks if the number has a divisor other than 1 and itself. If true, the function returns `false` as the number is not prime.

6. **Return Result:**
   - If no divisors were found, the function returns `true`, indicating that the number is prime.

## reverses an array:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract ArrayReverser {
    // Function to reverse an array of unsigned integers
    function reverseArray(uint256[] memory arr) public pure returns (uint256[] memory) {
        uint256 length = arr.length;
        uint256[] memory reversedArray = new uint256[](length);

        // Reverse the array
        for (uint256 i = 0; i < length; i++) {
            reversedArray[i] = arr[length - 1 - i];
        }

        return reversedArray;
    }
}
```

Explanation:

1. **Modifiers and Pragmas:**

   - `// SPDX-License-Identifier: MIT`: This is a SPDX license identifier specifying the license under which the contract is released.
   - `pragma solidity ^0.8.0;`: This pragma statement specifies that the contract is compatible with Solidity version 0.8.0 and higher.

2. **Contract Definition:**

   - `contract ArrayReverser { ... }`: This defines a Solidity contract named `ArrayReverser`.

3. **Function to Reverse an Array:**

   - `function reverseArray(uint256[] memory arr) public pure returns (uint256[] memory) { ... }`: This function takes an array of unsigned integers `arr` as input and returns a new array containing the elements of `arr` in reversed order. The function is marked as `pure` because it doesn't modify the state of the contract.

4. **Array Reversal:**

   - `uint256 length = arr.length;`: This line stores the length of the input array.
   - `uint256[] memory reversedArray = new uint256[](length);`: This line initializes a new array, `reversedArray`, with the same length as the input array.

5. **Reverse the Array:**

   - The `for` loop iterates through each element of the input array:
     - `reversedArray[i] = arr[length - 1 - i];`: This line assigns the elements of the input array in reversed order to the corresponding positions in the `reversedArray`.

6. **Return Result:**
   - The function returns the `reversedArray`.

## Sort an array : [Bubble Sort algorithm]:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract ArraySorter {
    // Function to sort an array of unsigned integers using Bubble Sort
    function sortArray(uint256[] memory arr) public pure returns (uint256[] memory) {
        uint256 length = arr.length;

        // Bubble Sort algorithm
        for (uint256 i = 0; i < length - 1; i++) {
            for (uint256 j = 0; j < length - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    // Swap elements if they are in the wrong order
                    (arr[j], arr[j + 1]) = (arr[j + 1], arr[j]);
                }
            }
        }

        return arr;
    }
}
```

Explanation:

1. **Modifiers and Pragmas:**

   - `// SPDX-License-Identifier: MIT`: This is a SPDX license identifier specifying the license under which the contract is released.
   - `pragma solidity ^0.8.0;`: This pragma statement specifies that the contract is compatible with Solidity version 0.8.0 and higher.

2. **Contract Definition:**

   - `contract ArraySorter { ... }`: This defines a Solidity contract named `ArraySorter`.

3. **Function to Sort an Array:**

   - `function sortArray(uint256[] memory arr) public pure returns (uint256[] memory) { ... }`: This function takes an array of unsigned integers `arr` as input and returns a new array containing the elements of `arr` in sorted order. The function is marked as `pure` because it doesn't modify the state of the contract.

4. **Array Sorting (Bubble Sort):**

   - The function uses the Bubble Sort algorithm to sort the input array.
   - The outer loop (`for (uint256 i = 0; i < length - 1; i++)`) represents the pass through the array.
   - The inner loop (`for (uint256 j = 0; j < length - i - 1; j++)`) represents the comparison and swapping of adjacent elements.

5. **Swap Elements:**

   - `if (arr[j] > arr[j + 1]) { (arr[j], arr[j + 1]) = (arr[j + 1], arr[j]); }`: This line checks if adjacent elements are in the wrong order, and if so, it swaps them.

6. **Return Result:**
   - The function returns the sorted array.

## simple linear search algorithm to find the index of an element in an array:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract ArraySearcher {
    // Function to search for an element in an array
    function searchElement(uint256[] memory arr, uint256 target) public pure returns (int256) {
        uint256 length = arr.length;

        // Linear search algorithm
        for (uint256 i = 0; i < length; i++) {
            if (arr[i] == target) {
                // Return the index if the element is found
                return int256(i);
            }
        }

        // Return -1 if the element is not found
        return -1;
    }
}
```

Explanation:

1. **Modifiers and Pragmas:**

   - `// SPDX-License-Identifier: MIT`: This is a SPDX license identifier specifying the license under which the contract is released.
   - `pragma solidity ^0.8.0;`: This pragma statement specifies that the contract is compatible with Solidity version 0.8.0 and higher.

2. **Contract Definition:**

   - `contract ArraySearcher { ... }`: This defines a Solidity contract named `ArraySearcher`.

3. **Function to Search for an Element:**

   - `function searchElement(uint256[] memory arr, uint256 target) public pure returns (int256) { ... }`: This function takes an array of unsigned integers `arr` and a target value `target` as input. It returns the index of the target element in the array or -1 if the element is not found. The function is marked as `pure` because it doesn't modify the state of the contract.

4. **Linear Search Algorithm:**

   - The function uses a simple linear search algorithm to iterate through the array.
   - `for (uint256 i = 0; i < length; i++) { ... }`: This loop iterates through each element of the array.
   - `if (arr[i] == target) { return int256(i); }`: This condition checks if the current element is equal to the target value. If true, it returns the index of the element.

5. **Return Result:**
   - If the element is found, the function returns the index. If the element is not found, it returns -1.

## finds the second-largest element:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract SecondLargestFinder {
    // Function to find the second-largest element in an array
    function findSecondLargest(uint256[] memory arr) public pure returns (uint256) {
        uint256 length = arr.length;

        // Ensure the array has at least two elements
        require(length >= 2, "Array must have at least two elements");

        uint256 largest = (arr[0] > arr[1]) ? arr[0] : arr[1];
        uint256 secondLargest = (arr[0] > arr[1]) ? arr[1] : arr[0];

        // Iterate through the array to find the largest and second-largest elements
        for (uint256 i = 2; i < length; i++) {
            if (arr[i] > largest) {
                secondLargest = largest;
                largest = arr[i];
            } else if (arr[i] > secondLargest && arr[i] < largest) {
                secondLargest = arr[i];
            }
        }

        return secondLargest;
    }
}
```

Explanation:

1. **Modifiers and Pragmas:**

   - `// SPDX-License-Identifier: MIT`: This is a SPDX license identifier specifying the license under which the contract is released.
   - `pragma solidity ^0.8.0;`: This pragma statement specifies that the contract is compatible with Solidity version 0.8.0 and higher.

2. **Contract Definition:**

   - `contract SecondLargestFinder { ... }`: This defines a Solidity contract named `SecondLargestFinder`.

3. **Function to Find the Second-Largest Element:**

   - `function findSecondLargest(uint256[] memory arr) public pure returns (uint256) { ... }`: This function takes an array of unsigned integers `arr` as input and returns the second-largest element. The function is marked as `pure` because it doesn't modify the state of the contract.

4. **Input Validation:**

   - `require(length >= 2, "Array must have at least two elements");`: This line ensures that the array has at least two elements. Finding the second-largest element requires at least two distinct elements.

5. **Initialization of Largest and Second-Largest:**

   - `uint256 largest = (arr[0] > arr[1]) ? arr[0] : arr[1];`: This line initializes the variable `largest` with the larger of the first two elements.
   - `uint256 secondLargest = (arr[0] > arr[1]) ? arr[1] : arr[0];`: This line initializes the variable `secondLargest` with the smaller of the first two elements.

6. **Find the Largest and Second-Largest Elements:**

   - The function iterates through the array starting from the third element (`for (uint256 i = 2; i < length; i++) { ... }`).
   - If the current element is larger than `largest`, it becomes the new `largest`, and the previous `largest` becomes the new `secondLargest`.
   - If the current element is larger than `secondLargest` but smaller than `largest`, it becomes the new `secondLargest`.

7. **Return Result:**
   - The function returns the second-largest element.
