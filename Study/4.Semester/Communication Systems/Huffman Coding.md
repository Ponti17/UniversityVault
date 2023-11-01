For an arbitrary message
$$ \textrm{message} \to BCCABBDDAECCBBAEDDCC $$
the cost of the message is the amount of bits. There are 20 letters. Each character are sent as an 8-bit ASCII code. 
$$ A = 01000001 $$
$$ B = 01000010 $$
$$ C = 01000011 $$
$$ D = 01000100 $$
$$ E = 01000101 $$
In total there will be sent $8*20 = 160$ bits. Since we are only transferring 5 different letters, 8-bit ASCII is unnecessary. We need 3 bits to represent 5 characters.
![[huff.png]]
When we use our new coding system the bit-length of the message will be $3 * 20 = 60$ bits. We need to also transmit the table that can decode the message. The total bits to describe ASCII $5 * 8 = 40$ bits plus the code $5 * 3 = 15$ bits. So the message is 60 bits and the table is 55 bits. In total 115 bits.

## Variable size coding
---
We arrange characters so they appear in increasing order of appearance
$$ E, A, D, B, C $$
Select two smallest and create a node. Repeat.
![[HuffNode.png]]
Write 0's on left and 1's on right. The codes are then given.
![[huffnodecode.png]]
![[huffcodesize.png]]