# EXP11-Huffman-Coding
# NAME : DEEPAKKUMAR S
# REG NO : 212225230042
# Aim
To implement Huffman coding to compress the data using Python.

#  Software Required
Anaconda - Python 3.7
# Algorithm:
Step1:
    Start the program and get the input string from the user.
Step2:
    Calculate the frequency of occurrence of each character in the string.
Step3:
    Create Huffman tree nodes using the character frequencies and combine the two lowest-frequency nodes repeatedly.
Step4:
    Assign 0 to the left branch and 1 to the right branch to generate Huffman codes.
Step5:
    Print each character along with its Huffman code.
# Program:

```

import heapq
from collections import Counter

# Get the input string
text = input("Enter the string: ")

# Calculate frequency of occurrence
freq = Counter(text)

# Create tree nodes
heap = [[weight, [char, ""]] for char, weight in freq.items()]
heapq.heapify(heap)

# Main function to implement Huffman coding
while len(heap) > 1:
    left = heapq.heappop(heap)
    right = heapq.heappop(heap)

    for pair in left[1:]:
        pair[1] = '0' + pair[1]

    for pair in right[1:]:
        pair[1] = '1' + pair[1]

    heapq.heappush(heap, [left[0] + right[0]] + left[1:] + right[1:])

# Print characters and their Huffman codes
print("Character and Huffman Code:")
for char, code in sorted(heap[0][1:], key=lambda x: x[0]):
    print(char, ":", code)

```


# Output:
<img width="347" height="165" alt="image" src="https://github.com/user-attachments/assets/6cac54a3-5e2a-4c09-ae8c-d2a815967105" />

# Result
Thus the huffman coding was implemented to compress the data using python programming.
