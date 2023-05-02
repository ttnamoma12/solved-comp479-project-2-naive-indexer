Download Link: https://assignmentchef.com/product/solved-comp479-project-2-naive-indexer
<br>
Objectives: Implement the naive indexer. Implement single term query processing. Implement and compare lossy dictionary compression.

Data: Use Reuters21578. For docID, use the NEWID values from the Reuters corpus to make your retrieval comparable. Make sure you access the sgm files and the docIDs in ascending order, this requires an extra step in Linux.

Description:

Subproject I: naive indexer

<ol>

 <li>develop a module that while there are still more documents to be processed, accepts a document as a list of tokens and outputs term-documentID pairs to a list F. Punctuation is not considered to be a token by itself, but your tokenizer might recognize tokens that include punctuation signs</li>

 <li>when there is no more input, sort F and remove duplicates</li>

 <li>turn the sorted file F into an index by turning the docIDs paired with the same term into a postings list</li>

 <li>find a way to determine, how much time your index takes to compile (not graded in this assignment)</li>

</ol>

Subproject II: single term query processing                                     Implement a query processor for single term queries, i.e.

queries that consist exclusively of one term

<ol>

 <li>Input: one term</li>

 <li>Output: append term to postings list. Make sure that the postings list is ordered 3. turn your output into json format:</li>

</ol>

Listing 1: Python example

import json

<em>#Submit       your       queries       in     the        following         format :</em>

<em># 1. &lt;query1&gt; </em>−<em>&gt; replace               with      the         corresponding         query       string</em>

<em># 2.             [1 ,2 ,4] </em>−<em>&gt; replace            with      the         corresponding           postings       l i s t</em>

<em># 3. change the filename “sampleQueries . json” for the appropriate situation </em>q = {“&lt;query1&gt;” : [1 ,2 ,4] , “&lt;query2&gt;” : [2 ,3] , “&lt;query3&gt;” : [1 ,4]}

json .dump(q , open(“sampleQueries . json” ,”w” , encoding=”utf−8″) , indent=3) 4. validate query returns for three sample queries (you have to decide on your sample queries)

1

Subproject III: implement lossy dictionary compression, ‘recreate’ Table 5.1 columns 1 and 2

<ol>

 <li>implement the lossy dictionary compression techniques of Table 5.1 in the textbook and compile a similar table for Reuters-21578 for dictionary and non-positional index. Are the changes similar? Discuss your findings. (Note that stemming is not required here, if you run out of time before you get the Porter stemmer to work, that is ok for this assignment, the remaining table is fine.) To use a unified list of 30 and 150 stop words, use https://teacherjoe.us/Vocab200.html (first 30 and first 150 words respectively)</li>

 <li>compare retrieval results for your three sample queries of Subproject II when you run them on your compressed index. Discuss your findings in your report</li>

</ol>

Deliverables:

<ol>

 <li>individual project</li>

 <li>well documented code</li>

 <li>“sampleQueries.json”: output of your three sample queries in json format as described</li>

 <li>“challengeQueries.json”: output of the queries posted two days before the deadline in json format as described. Run queries on both indices</li>

 <li>any additional testing or aborted design ideas that show off particular aspects of your project</li>

 <li>a project report that summarizes your approach, illustrates your designs, presents your table of savings for lossy dictionary compression and discusses, what you have learned from the project https://teacherjoe.us/Vocab200.html Marks:</li>

</ol>