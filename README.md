# File-Zipper-Using-Huffman-Coding

https://youtu.be/RfYf2IMNDo0-For Explanation- Huffman Coding C++

Huffman Coding is a technique of compressing data to reduce its size without losing any of the details. It was first developed by David Huffman.Huffman Coding is generally useful to compress the data in which there are frequently occurring characters.
How Huffman Coding works?
Suppose the string below is to be sent over a network.
![image](https://user-images.githubusercontent.com/93857300/216992358-c1d58c68-4edb-4366-a1fd-5a4de27c21af.png)

Each character occupies 8 bits. There are a total of 15 characters in the above string. Thus, a total of 8 * 15 = 120 bits are required to send this string.
Using the Huffman Coding technique, we can compress the string to a smaller size.
Huffman coding first creates a tree using the frequencies of the character and then generates code for each character.

Once the data is encoded, it has to be decoded. Decoding is done using the same tree.

Huffman Coding prevents any ambiguity in the decoding process using the concept of prefix code ie. a code associated with a character should not be present in the prefix of any other code. The tree created above helps in maintaining the property.

Huffman coding is done with the help of the following steps.

1.Calculate the frequency of each character in the string.
![image](https://user-images.githubusercontent.com/93857300/216992452-755c10c5-84dc-4721-9f79-b321a993e691.png)

2.Sort the characters in increasing order of the frequency. These are stored in a priority queue Q.
![image](https://user-images.githubusercontent.com/93857300/216992521-50e18f1b-93a5-4eb9-a2dd-82a6edfb0c1d.png)

3.Make each unique character as a leaf node.

4.Create an empty node z. Assign the minimum frequency to the left child of z and assign the second minimum frequency to the right child of z. Set the value of the z as the sum of the above two minimum frequencies.

![image](https://user-images.githubusercontent.com/93857300/216992596-8f214581-782f-4335-a7db-005251e46fa6.png)

5.Remove these two minimum frequencies from Q and add the sum into the list of frequencies (* denote the internal nodes in the figure above).

6.Insert node z into the tree.

7.Repeat steps 3 to 5 for all the characters.

![image](https://user-images.githubusercontent.com/93857300/216992693-10e863d8-4802-4e6a-b2c0-a1b3a72b2590.png)

![image](https://user-images.githubusercontent.com/93857300/216992712-cade0af5-cf30-402d-aebe-62e0ebc97313.png)

8.For each non-leaf node, assign 0 to the left edge and 1 to the right edge

![image](https://user-images.githubusercontent.com/93857300/216992839-f8afe125-65c4-4312-a37c-43fc2ed3a87e.png)

<img width="571" alt="image" src="https://user-images.githubusercontent.com/93857300/216992905-24a3456e-15f9-4c93-b793-a7b7c7f0eb29.png">

Without encoding, the total size of the string was 120 bits. After encoding the size is reduced to 32 + 15 + 28 = 75.

**Decoding the code**
For decoding the code, we can take the code and traverse through the tree to find the character.

![image](https://user-images.githubusercontent.com/93857300/216993057-7233132f-5d1c-44b7-9f6f-770bdeae5c9f.png)

