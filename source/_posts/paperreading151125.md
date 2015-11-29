title: paper reaing 151125 
---
---
2015 ICML: From Word Embedding to Document Distances
---
一般来说，计算两个doc的相似度的方式很多。一种是先对原始的doc构建一个表达，将两个doc的相似度计算转化成两个表达的相似度计算，一个比较通用的做法是将doc表示成一个向量。构建doc表达的方式有很多种：[BOW/TF-IDF][6]、[Latent Semantic Indexing(LSI)][1]、[Latent Dirichlet Allocation(LDA)][2] 以及[PV-DBOW][3] 等等，这个也是目前比较主流的一些做法。 另一种是基于doc中meta-data的相似度来构建doc的相似度，这里的meta data可以是doc的topic[7]或者word等。这篇文章就是属于后面一种，基于word对之间的相似度来构建doc对之间的相似度。
#motivation
假设有两个doc D1和D2，我们要计算这两个句子的相似度。

* D1: <font color="#0030cf">obama</font> <font color="#ff0000">speaks</font> to the <font color="00ff00">media</font> in <font color="#23dfcc">Illinois</font>.
* D2: The <font color="#0030cf">President</font> <font color="ff0000">greets</font> the <font color="#00ff00">press</font> in <font color="#23dfcc">Chicago</font>.

很明显的，传统基于BOW/TF-IDF的相似度计算方式的话D1和D2之间的相似度是0（stop word 被移除了）.而实际上这两个句子其实是说的同一个事情，只是用了不同词而已。

#background
##word embedding
词向量这几年可以说是NLP里面最火的，有很多做词向量学习的文章，影响力比较大的就是Mikolov搞的[word2vec][4]了。直接上个图：
![word2vec](../pic/20151125_w2v.png "word2vec")
可以看到一个词被表示成一个向量后，在这个向量空间中，相似的词距离比较小。
##earth mover's distance(EMD)
![EMD](../pic/20151125_emd.png "Earth Mover's Distance")
EMD是用来计算两个分布之间的相似度的。如图中两个分布P和Q，其中分布P中每个元素Pi都有自己的capacity，如图中P1的capacity为0.4，而Q1的capacity是 $p\_i$
<img src="http://www.forkosh.com/mathtex.cgi? \Large x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}">
#refrence
[1]: <http://www.baidu.com> "LSI"

[2]: <http://www.baidu.com> "LDA"

[3]: <http://www.baidu.com> "PV-DBOW"

[4]: <http://www.baidu.com> "word2vec"

[5]: <http://www.baidu.com> "EMD"

[6]: <http://www.baidu.com> "TF-IDF"

[7]: <http://www.baidu.com> "wanxiaojun"