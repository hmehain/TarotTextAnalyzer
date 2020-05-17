# Implementation Stage 1
Simple Java program with console output. Finds the frequency of words in the text. (Requirements 1 & 2.1)

We will use a trie to store the letters in each word. Each word will also have the associated number of times it is found. 
We will hardcode a sample text and use it. This is the sample text we will use from the Master card in the Osho Zen Tarot which can be found here: https://www.osho.com/iosho/zen-tarot/.

"The Master in Zen is not a master over others, but a master of himself, and this self-mastery is reflected in his every gesture and his every word. He is not a teacher with a doctrine to impart, nor a supernatural messenger with a direct line to God, but simply one who has become a living example of the highest potential that lies within each and every human being. In the eyes of the Master, a disciple finds his own truth reflected. In the silence of the Master's presence, the disciple can fall more easily into the silence of his own being. The community of seekers that arises around a Master becomes an energy field that supports each unique individual in finding his or her own inner light. Once that light is found, the disciple comes to understand that the outer Master was just a catalyst, a device to provoke the awakening of the inner.

Beyond mind, there is an awareness that is intrinsic, that is not given to you by the outside, and is not an idea, and there is no experiment up to now that has found any center in the brain which corresponds to awareness. The whole work of meditation is to make you aware of all that is "mind" and disidentify yourself from it. That very separation is the greatest revolution that can happen to man.

Now you can do and act on only that which makes you more joyous, fulfills you, gives you contentment, makes your life a work of art, a beauty. But this is possible only if the master in you is awake. Right now the master is fast asleep. And the mind, the servant, is playing the role of master. And the servant is created by the outside world, it follows the outside world and its laws.

Once your awareness becomes a flame, it burns up the whole slavery that the mind has created. There is no blissfulness more precious than freedom, than being a master of your own destiny."

## Step 0 Create data structure. 
Each node in the trie contains a char, boolean endOfWord, int count, and a list of its children. 
If you are at the end of the word, you need to know the number of times this word is found (count).
For the list of children, we could use a priority queue.
When we search the trie, we will look for the least used letter. 
When we add a word to the trie, we will likely want to search the most used letter first,
because it is more likely that it will belong to the word we are using. 
Therefore, searching for the right letter is best case O(1). 
We multiply that by the average length of the word. 
Using a priority queue in Java has O(logn) runtime complexity to insert an element. 
We would insert an element every time a new sequence of letters comes up, which will be often until words start repeating.
Another alternative for the list of children is using a hashmap.
An element can be found and inserted in O(1) in the worst case. 
However, search for the element with the highest count is O(n).
It is only necessary to do that when you are searching the trie to find the least used words.
Let n = number words. Let l = average length of words. Let's assume a 20% ratio of unique words. 
The total number of characters is l x n. Assume that 80% of these characters are completely repeated, and no insertions are necessary.
Of the other 20%, let's assume that 30% of these have the same root. Therefore, 0.7 x 20% = 14% of the total number of characters
will be new insertions. 
Runtime for creating trie = (n x l)(time to search for right child + 0.14(time to insert character))
Runtime for searching trie = l x (time to find min character) x (# words looking for)
The number of characters in the list of children is maximum 26, and is represented by c.

Priority Queue: 
Time to search for right child = Close to O(1)
Time to insert character = O(logc)
Time to find min character = O(c)
Runtime for creating trie = (n x l)(Close to O(1) + 0.14(logc))
Runtime for searching trie = l x (O(c)) x (# words looking for)

HashMap
Time to search for right child = O(1)
Time to insert character = O(1)
Time to find min character = O(c)
Runtime for creating trie = (n x l)(O(1) + 0.14(O(1)))
Runtime for searching trie = l x (O(c)) x (# words looking for)

We can clearly see that for our purposes, a HaspMap has a more efficient runtime than a priority queue because the time
to insert a character is O(1) instead of O(logc). If we keep track of the number of words (n), a running total of the number 
of characters processed (which can give us the average number of characters in each word (l), the number of insertions made, 
and the number of repeated words, we can calculate the proportion of less operations required using a HashMap over a Priority Queue. 


## Step 1 Store words in trie.


## Step 2 Search trie to find the least used words.


