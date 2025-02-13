The MD5 hashing algorithm is a message-bsaed 128 bit hashing algorithm, it is a block algorithm that computes the hash in four different sections, computing the next block based off of the prvious block and so on, four times.

SHA or secure hash algorithms can be broken down into two different types, SHA-3 and SHA-256. 
SHA-3 is made by someone different than who made SHA-256 and features different block sizes, with the most common being 1600 bits. Furthermore, the output size is variable, between 224, 256, 384, and 512.  
SHA-256 is made by NSA and features a static block size of 512 bits, with an output size of 256, these values are both static and low compaired to SHA-3, which makes SHA-256 faster, if less secure.

Bcyrpt is the most secure of all of the previous hash functions and also generates passwords rather than strictly encrypting data, it uses an adaptive function to fluctuate and lengthen to stay protected against brute force attacks. It is the default hash algorithm for certain linux distributions. It uses a salt value, which is a string of random characters to further boost security for oneway functions. This salt is 128-bits.
