# bitcoin

keyword: concursys job  

1. How bitcoin concensus protocol change diffculty?  
Each node uses same protocol, and they always see same block-chain, they calculate diffculty based on the time that last 2016 blocks takes, because they use same algorithm so they share same diffculty.  

2. How bitcoin node get same puzzle at begining of mine?  
similar as first question, they always see same blockchain and they just get the puzzle based on blockchain with same algorithm  

# Radix Tree
![alt text](image.png)

# Merkel Tree
In cryptography and computer science, a hash tree or Merkle tree is a tree in which every "leaf" node is labelled with the cryptographic hash of a data block, and every node that is not a leaf (called a branch, inner node, or inode) is labelled with the cryptographic hash of the labels of its child nodes. A hash tree allows efficient and secure verification of the contents of a large data structure. A hash tree is a generalization of a hash list and a hash chain.

The concept of a hash tree is named after Ralph Merkle, who patented it in 1979

In bicoin, a chain node contains a Merkel Tree that including all trades, I think not every node of bitcoin is available to storge all that chain node, so if they want to prove that some trade is in this chain node, they just need receive several hash and calculate the root hash and compare.
But if they want to prove some trade is not in the Merkel Tree, they have to see the whole tree and walk through the leaf nodes.

Attention: In bitcoin, if trade num cannot be divided by 2, some trade will be copied to it's brother node.  
![alt text](image-1.png)

# Sparse Merkle Tree 稀疏默克尔树
Every node has a index, and leaf node allowed to be None, prove exist is same as Merkel Tree, prove not exist just think that node's value is hash(None) and calculate with orther hashs then get root hash.
![alt text](image-2.png)

# Merkle Patricia Trie, MPT(默克尔压缩前缀树)
https://learnblockchain.cn/books/geth/part3/mpt.html  
以太坊不同于比特币的 UXTO 模型，在账户模型中，账户存在多个属性（余额、代码、存储信息），属性（状态）需要经常更新。因此需要一种数据结构来满足几点要求：

①在执行插入、修改或者删除操作后能快速计算新的树根，而无需重新计算整个树。  
②即使攻击者故意构造非常深的树，它的深度也是有限的。否则，攻击者可以通过特意构建足够深的树使得每次树更新变得极慢，从而执行拒绝服务攻击。  
③树的根值仅取决于数据，而不取决于更新的顺序。以不同的顺序更新，甚至是从头重新计算树都不会改变树的根值。  
要求①是默克尔树特性，但要求②③则非默克尔树的优势。 对于要求②，可将数据 Key 进行一次哈希计算，得到确定长度的哈希值参与树的构建。而要求③则是引入位置确定的压缩前缀树并加以改进。  





