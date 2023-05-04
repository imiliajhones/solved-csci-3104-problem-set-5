Download Link: https://assignmentchef.com/product/solved-csci-3104-problem-set-5
<br>
<ol>

 <li>(15 pts) Bellatrix Lestrange is writing a secret message to Voldemort and wants to prevent it from being understood by meddlesome young wizards and Muggles. She decides to use Huffman encoding to encode the message. Magically, the symbol frequencies of the message are given by the <em>Pell numbers</em>, a famous sequence of integers known since antiquity and related to the <em>Fibonacci numbers</em>. The <em>n</em>th Pell number is defined as <em>P<sub>n </sub></em>= 2<em>P<sub>n</sub></em><sub>−1 </sub>+ <em>P<sub>n</sub></em><sub>−2 </sub>for <em>n &gt; </em>1 with base cases <em>P</em><sub>0 </sub>= 0 and <em>P</em><sub>1 </sub>= 1.

  <ul>

   <li>For an alphabet of Σ = {<em>a,b,c,d,e,f,g,h</em>} with frequencies given by the first |Σ| non-zero Pell numbers, give an optimal Huffman code and the corresponding encoding tree for Bellatrix to use.</li>

   <li>Generalize your answer to (1a) and give the structure of an optimal code whenthe frequencies are the first <em>n </em>non-zero Pell numbers.</li>

  </ul></li>

 <li>(30 pts) A good hash function <em>h</em>(<em>x</em>) behaves in practice very close to the uniform hashing assumption analyzed in class, but is a deterministic function. That is, <em>h</em>(<em>x</em>) = <em>k </em>each time <em>x </em>is used as an argument to <em>h</em>(). Designing good hash functions is hard, and a bad hash function can cause a hash table to quickly exit the sparse loading regime by overloading some buckets and under loading others. Good hash functions often rely on beautiful and complicated insights from number theory, and have deep connections to pseudorandom number generators and cryptographic functions. In practice, most hash functions are moderate to poor approximations of uniform hashing.</li>

</ol>

Consider the following hash function. Let <em>U </em>be the universe of strings composed of the characters from the alphabet Σ = [A<em>,…,</em>Z], and let the function <em>f</em>(<em>x<sub>i</sub></em>) return the index of a letter <em>x<sub>i </sub></em>∈ Σ, e.g., <em>f</em>(A) = 1 and <em>f</em>(Z) = 26. Finally, for an <em>m</em>-character string <em>x </em>∈ Σ<em><sup>m</sup></em>, define ), where <em>` </em>is the number of buckets in the hash table. That is, our hash function sums up the index values of the characters of a string <em>x </em>and maps that value onto one of the <em>` </em>buckets.

<ul>

 <li>The following list contains US Census derived last names:</li>

</ul>

http://www2.census.gov/topics/genealogy/1990surnames/dist.all.last Using these names as input strings, first choose a uniformly random 50% of these name strings and then hash them using <em>h</em>(<em>x</em>).

Produce a histogram showing the corresponding distribution of hash locations when <em>` </em>= 200. Label the axes of your figure. Briefly describe what the figure shows about <em>h</em>(<em>x</em>), and justify your results in terms of the behavior of <em>h</em>(<em>x</em>). Do not forget to append your code.

Hint: the raw file includes information other than name strings, which will need to be removed; and, think about how you can count hash locations without building or using a real hash table.

1

<ul>

 <li>Enumerate at least 4 reasons why <em>h</em>(<em>x</em>) is a bad hash function relative to the ideal behavior of uniform hashing.</li>

 <li>Produce a plot showing (i) the length of the longest chain (were we to use chainingfor resolving collisions under <em>h</em>(<em>x</em>)) as a function of the number <em>n </em>of these strings that we hash into a table with <em>` </em>= 200 buckets, (ii) the exact upper bound on the depth of a red-black tree with <em>n </em>items stored, and (iii) the length of the longest chain were we to use a uniform hash instead of <em>h</em>(<em>x</em>). Include a guide of <em>cn</em></li>

</ul>

Then, comment (i) on how much shorter the longest chain would be under a uniform hash than under <em>h</em>(<em>x</em>), and (ii) on the value of <em>n </em>at which the red-black tree becomes a more efficient data structure than <em>h</em>(<em>x</em>) and separately a uniform hash.

<ol start="3">

 <li>(15 pts) Draco Malfoy is struggling with the problem of making change for <em>n </em>cents using the smallest number of coins. Malfoy has coin values of <em>v</em><sub>1 </sub><em>&lt; v</em><sub>2 </sub><em>&lt; </em>·· <em>&lt; v<sub>r </sub></em>for <em>r </em>coins types, where each coin’s value <em>v<sub>i </sub></em>is a positive integer. His goal is to obtain a set of counts {<em>d<sub>i</sub></em>}, one for each coin type, such that and where <em>k </em>is minimized.</li>

</ol>

(a) A greedy algorithm for making change is the <strong>cashier’s algorithm</strong>, which all young wizards learn. Malfoy writes the following pseudocode on the whiteboard to illustrate it, where <em>n </em>is the amount of money to make change for and <em>v </em>is a

vector of the coin denominations:

wizardChange(n,v,r) :

d[1 .. r] = 0 // initial histogram of coin types in solution while n &gt; 0 {

k = 1 while ( k &lt; r and v[k] &gt; n ) { k++ } if k==r { return ’no solution’ } else { n = n – v[k] }

} return d

Hermione snorts and says Malfoy’s code has bugs. Identify the bugs and explain why each would cause the algorithm to fail.

<ul>

 <li>Sometimes the goblins at Gringotts Wizarding Bank run out of coins,<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a> and make change using whatever is left on hand. Identify a set of U.S. coin denominations for which the greedy algorithm does not yield an optimal solution. Justify your</li>

</ul>

2

answer in terms of optimal substructure and the greedy-choice property. (The set should include a penny so that there is a solution for every value of <em>n</em>.)

<ul>

 <li>(8 pts extra credit) On the advice of computer scientists, Gringotts has announcedthat they will be changing all wizard coin denominations into a new set of coins denominated in powers of <em>c</em>, i.e., denominations of <em>c</em><sup>0</sup><em>,c</em><sup>1</sup><em>,…,c<sup>` </sup></em>for some integers <em>c &gt; </em>1 and <em>` </em>≥ 1. (This will be done by a spell that will magically transmute old coins into new coins, before your very eyes.) Prove that the cashier’s algorithm will always yield an optimal solution in this case.</li>

</ul>

Hint: first consider the special case of <em>c </em>= 2.

3

<a href="#_ftnref1" name="_ftn1">[1]</a> It’s a little known secret, but goblins like to <em>eat </em>the coins. It isn’t pretty for the coins, in the end.