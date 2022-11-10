# Web Search Engine

The objective of the project is to implement a web search engine using the Page Ranking and HITS Algorithms.






## Page Ranking
The Page Ranking Algorithm provides the static ranking of the web pages based on the connections between them.

The page having more connections with other pages has a grater probability of being opened, thus having a better ranking.

Two methods have been used for the page ranking algorithm:
* Left Principle Eigenvalue Vector Method
* Power Iteration Method

Random Teleportation between web pages has also been considered, i.e
a user can navigate from one page to another even in the absence of a link between two web pages
by directly typing the URL of the target web page.
## HITS Algorithm
The Hyperlink Induced Topic Search (HITS) Algorithm is a dynamic page ranking algorithm
that ranks pages as per the query inputted by the user.

The ranking is done on the basis of the Hub and Authority scores of the pages.

In general, a good hub is a page that points to several good authorities; a good authority is a page indicated to by several good hubs.

In our project, we output the top 3 Hub and Authority pages for the query given by the user.

**Input Formatting and Preprocessing**
* The input is in the form of a web_graph.gpickle file, which we convert to a numpy array.
* Then we preprocess the data of each web page by removing punctuations and stopwords and by normalizing the words using Porter Stemmer.
* Then we construct an Inverted Index (Dictionary) with keys as all the unique words in our vocabulary and values as the indices of the web-pages containing those words.

**Page Ranking**
* We consider the web-pages that satisfy the user query and the pages that are directly linked to these pages.
* We then use the Principle Eigenvector Method to find the top 3 Hub and Authority pages for the given query.
