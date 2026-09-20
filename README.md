# DIPT-EXP-11-IMPLEMENTATION-OF-HUFFMAN-CODING

## Name : Harish S

## Reg no : 212224240052

## Aim
To implement Huffman coding to compress the data using Python.

## Software Required
1. Anaconda - Python 3.7

## Algorithm:
### Step1:
Get the input string.

### Step2:
Create tree nodes.

### Step3:
Main function to implement huffman coding.

### Step4:
calculate frequency of occurence.

### Step5:
print the characters and its huffmancode.
 
## Program:


``` Python

input_string = "Harish SEC"
frequency = {}
for char in input_string:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1
nodes = [[char, freq] for char, freq in frequency.items()]
while len(nodes) > 1:
    # Sort nodes based on frequency
    nodes = sorted(nodes, key=lambda x: x[1])

    # Pick two smallest nodes
    left = nodes.pop(0)
    right = nodes.pop(0)

    # Create a new node with combined frequency
    new_node = [[left, right], left[1] + right[1]]
    nodes.append(new_node)

# The final node is the Huffman tree
huffman_tree = nodes[0]
huffman_codes = {}

def generate_codes(tree, code=""):
    if isinstance(tree[0], str):  # If it's a leaf node
        huffman_codes[tree[0]] = code
    else:  # If it's an internal node, recurse
        generate_codes(tree[0][0], code + "0")
        generate_codes(tree[0][1], code + "1")

generate_codes(huffman_tree)
print("Character | Harish (SEC)")
print("-------------------------")
for char, code in huffman_codes.items():
    print(f"    {char}    |    {code}")


```
## Output:

### Print the characters and its huffmancode

<img width="362" height="280" alt="image" src="https://github.com/user-attachments/assets/29022771-ed7f-4b38-8799-572339862b22" />



## Result
Thus the huffman coding was implemented to compress the data using python programming.
