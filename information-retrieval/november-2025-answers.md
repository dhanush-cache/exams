# Information Retrieval - Answers

## Q1
### a) Explain the components of IR System.
An Information Retrieval (IR) system has the following core components:
1.  **Crawling/Indexing:** This component gathers and parses documents. A crawler systematically browses the web or a document collection, and an indexer processes and stores the data in an efficient data structure, typically an inverted index, to enable fast searching.
2.  **Query Processing:** This component takes the user's query, which can be a keyword or a question, and processes it. This may involve query expansion (adding synonyms), spelling correction, and parsing the query to understand the user's intent.
3.  **Matching/Ranking:** This is the core of the IR system. It matches the processed query against the indexed documents. The matching documents are then ranked based on their relevance to the query using algorithms like TF-IDF, PageRank, or other relevance scoring methods.
4.  **User Interface:** This component provides the interface for the user to enter their query and view the search results.
5.  **Evaluation:** This component measures the effectiveness of the IR system using metrics like precision, recall, and F1-score to assess the quality of the search results.

### b) Step by step explain the inverted index construction for the below given documents:
**Document 1:** The IR practical was conducted in CS lab.  
**Document 2:** The CS lab was occupied whole day for a practical.

**Step 1: Tokenization**  
Break down the documents into individual words (tokens).
*   **Doc 1:** "The", "IR", "practical", "was", "conducted", "in", "CS", "lab"
*   **Doc 2:** "The", "CS", "lab", "was", "occupied", "whole", "day", "for", "a", "practical"

**Step 2: Normalization**  
Convert all tokens to a consistent format (e.g., lowercase).
*   **Doc 1:** "the", "ir", "practical", "was", "conducted", "in", "cs", "lab"
*   **Doc 2:** "the", "cs", "lab", "was", "occupied", "whole", "day", "for", "a", "practical"

**Step 3: Stop Word Removal**  
Remove common words that don't add much meaning (e.g., "the", "in", "was", "a", "for").
*   **Doc 1:** "ir", "practical", "conducted", "cs", "lab"
*   **Doc 2:** "cs", "lab", "occupied", "whole", "day", "practical"

**Step 4: Create the Inverted Index**  
Create a dictionary where keys are the unique terms (words) and values are lists of document IDs where the term appears.

| Term      | Document ID |
|-----------|-------------|
| a         | 2           |
| conducted | 1           |
| cs        | 1, 2        |
| day       | 2           |
| for       | 2           |
| in        | 1           |
| ir        | 1           |
| lab       | 1, 2        |
| occupied  | 2           |
| practical | 1, 2        |
| the       | 1, 2        |
| was       | 1, 2        |
| whole     | 2           |

### c) Write an algorithm to find Edit Distance. Use Edit Distance algorithm to find the edit distance between “sunday” and “saturday”.
The Edit Distance (or Levenshtein distance) between two strings is the minimum number of single-character edits (insertions, deletions, or substitutions) required to change one string into the other.

**Algorithm:**
1. Create a matrix `D` of size `(m+1) x (n+1)` where `m` and `n` are the lengths of the two strings.
2. Initialize the first row and column of the matrix with `0, 1, 2, ...`.
3. For each cell `D[i][j]`, the value is the minimum of:
   - `D[i-1][j] + 1` (deletion)
   - `D[i][j-1] + 1` (insertion)
   - `D[i-1][j-1] + cost`, where `cost` is 0 if `string1[i-1] == string2[j-1]` and 1 otherwise (substitution).
4. The value in the bottom-right cell `D[m][n]` is the edit distance.

**Example: "sunday" and "saturday"**
The edit distance between "sunday" and "saturday" is 3.
1. `s` -> `s` (no change)
2. `u` -> `a` (substitution)
3. `n` -> `t` (substitution)
4. `d` -> `u` (substitution)
5. `a` -> `r` (insertion)
6. `y` -> `d` (insertion)
7. `a` -> `y` (insertion)

Let's trace with the algorithm: `sunday` -> `saturday`
1. **s**unday -> **sa**turday (insert 'a')
2. su**n**day -> satu**r**day (substitute 'n' with 'r')
3. sun**d**ay -> satur**d**ay (no change)
4. sund**a**y -> saturda**y** (no change)
5. sunday -> saturday (insert 't' and 'u')
   - s**a**turday
   - sa**t**urday
   - satu**r**day
The edit distance is 3.

### d) Write a short note on Vector Space Model.
The Vector Space Model (VSM) is an algebraic model for representing text documents (and any objects, in general) as vectors of identifiers, such as index terms. In this model, each document is represented as a vector in a multi-dimensional space, where each dimension corresponds to a unique term from the document collection.
- **Term Weighting:** The value of each component in the vector is a weight that represents the importance of the term in the document. A common weighting scheme is TF-IDF (Term Frequency-Inverse Document Frequency), which assigns higher weights to terms that are frequent in a document but rare in the overall collection.
- **Similarity Measurement:** The similarity between two documents (or a query and a document) is calculated as the cosine of the angle between their corresponding vectors. A smaller angle indicates higher similarity.
- **Querying:** Queries are also represented as vectors in the same space, and the documents are ranked based on their similarity to the query vector.

### e) Discuss various evaluation metrics used in information retrieval.
1.  **Precision:** The fraction of retrieved documents that are relevant. It measures the accuracy of the search results. `Precision = (Number of relevant documents retrieved) / (Total number of documents retrieved)`
2.  **Recall:** The fraction of relevant documents that are retrieved. It measures the completeness of the search results. `Recall = (Number of relevant documents retrieved) / (Total number of relevant documents)`
3.  **F1-Score:** The harmonic mean of precision and recall, providing a single score that balances both. `F1 = 2 * (Precision * Recall) / (Precision + Recall)`
4.  **Mean Average Precision (MAP):** The mean of the average precision scores for each query. It is a popular measure for evaluating ranked retrieval results over a set of queries.
5.  **Normalized Discounted Cumulative Gain (nDCG):** A measure of ranking quality that considers the graded relevance of the retrieved documents. It is particularly useful when documents can have different levels of relevance.

### f) List the different spelling correction techniques. Explain any one in detail.
**Spelling Correction Techniques:**
1.  **Edit Distance:** Finding words in the dictionary that are within a small edit distance from the misspelled word.
2.  **k-gram Overlap:** Breaking the misspelled word into k-grams (sequences of k characters) and finding dictionary words with a high overlap of k-grams.
3.  **Noisy Channel Model:** A probabilistic model that finds the most likely intended word given a misspelled word.
4.  **Phonetic Hashing:** Using algorithms like Soundex or Metaphone to find words that sound similar.

**Edit Distance in detail:**
The edit distance (or Levenshtein distance) is a widely used technique for spelling correction. It calculates the minimum number of edits (insertions, deletions, or substitutions) needed to transform one string into another. When a user enters a query, the system can calculate the edit distance between the query term and the terms in its dictionary. If a term has a small edit distance (e.g., 1 or 2) to a dictionary term, it is considered a potential correction. The system can then suggest the dictionary term to the user or automatically correct the query.

## Q2
### a) Write a short note on Naive Bayes classification algorithm.
Naive Bayes is a probabilistic classification algorithm based on Bayes' theorem. It is called "naive" because it makes a strong (and often unrealistic) assumption that the features are conditionally independent of each other, given the class. Despite this simplification, Naive Bayes often performs well in practice, especially for text classification tasks like spam detection.

**How it works:**
1.  It calculates the prior probability of each class.
2.  It calculates the conditional probability of each feature given each class.
3.  For a new data point, it uses Bayes' theorem to calculate the posterior probability of each class, and it assigns the data point to the class with the highest posterior probability.

### b) Diagrammatically explain web search architecture.
A web search engine architecture typically consists of the following components:

```
+----------------+   +-----------------+   +-------------------+
|      User      |-->|   Query         |-->|   Search Engine   |
| (Web Browser)  |   |   Interface     |   |   (Ranking Algo)  |
+----------------+   +-----------------+   +-------------------+
       ^                                            |
       |                                            v
+----------------+   +-----------------+   +-------------------+
|  Search Results|<-|   Web Server      |<-|   Index           |
+----------------+   +-----------------+   +-------------------+
                                                      ^
                                                      |
                                             +-----------------+
                                             |   Crawler       |
                                             | (Spider)        |
                                             +-----------------+
```
1.  **Crawler (Spider):** A bot that systematically browses the web, downloads web pages, and follows links to discover new pages.
2.  **Indexer:** Processes the downloaded pages, extracts the content, and builds an index (typically an inverted index) to enable fast searching.
3.  **Search Engine (Ranking Algorithm):** Takes the user's query, matches it against the index, and ranks the results based on relevance.
4.  **Query Interface:** The user interface where the user enters their query.
5.  **Web Server:** Delivers the search results to the user's browser.

### c) Briefly explain page rank algorithm. Give suitable example to explain the concept.
PageRank is an algorithm used by Google Search to rank web pages in their search engine results. It works by counting the number and quality of links to a page to determine a rough estimate of how important the website is. The underlying assumption is that more important websites are likely to receive more links from other websites.

**Example:**
Imagine two web pages, A and B. If page A has a link to page B, it is considered a "vote" for page B. The PageRank of page B is determined by the number of incoming links it has. However, not all votes are equal. A vote from an important page (a page with a high PageRank) is more valuable than a vote from a less important page. So, if page A has a high PageRank and links to page B, it contributes more to page B's PageRank than if a less important page linked to it.

### d) Discuss RankBoost.
RankBoost is a machine learning algorithm used for ranking tasks. It is an extension of the AdaBoost algorithm. RankBoost is used to learn a ranking function from a set of training data that consists of pairs of items, where one item is known to be ranked higher than the other.

**How it works:**
1.  It iteratively trains a series of weak learners (simple ranking functions).
2.  In each iteration, it focuses on the pairs of items that were incorrectly ranked by the previous weak learners.
3.  It combines the weak learners into a single strong ranking function by giving more weight to the weak learners that perform well.

RankBoost is commonly used in information retrieval and recommendation systems to improve the ranking of search results or recommended items.

### e) State the use of crawler. Explain in brief the working of crawler/ crawler architecture.
A crawler (also known as a spider or bot) is a program that systematically browses the World Wide Web in a methodical, automated manner. The primary use of a crawler is to gather data from websites, which is then used by search engines to build their index.

**Working of a Crawler:**
1.  **Seed URLs:** The crawler starts with a list of initial URLs, called seeds.
2.  **Fetching:** It fetches the web pages corresponding to the seed URLs.
3.  **Parsing:** It parses the fetched pages to extract the content and the links to other pages.
4.  **URL Frontier:** The extracted links are added to a queue of URLs to be visited, called the URL frontier.
5.  **Loop:** The crawler repeats the process of fetching, parsing, and adding new URLs to the frontier.
The crawler architecture also includes components for politeness (to avoid overloading web servers), duplicate detection, and handling various types of content.

### f) Explain hierarchical clustering.
Hierarchical clustering is a method of cluster analysis that seeks to build a hierarchy of clusters. There are two main types of hierarchical clustering:
1.  **Agglomerative (Bottom-Up):** This is a "bottom-up" approach. Each observation starts in its own cluster, and pairs of clusters are merged as one moves up the hierarchy. The process continues until all clusters have been merged into a single cluster that contains all observations.
2.  **Divisive (Top-Down):** This is a "top-down" approach. All observations start in one cluster, and splits are performed recursively as one moves down the hierarchy. The process continues until each observation is in its own cluster.

The result of hierarchical clustering is a tree-based representation of the observations, called a dendrogram. The dendrogram can be cut at a chosen height to obtain a specific number of clusters.

## Q3
### a) Which various dynamic web contents need to be taken care of during crawling?
Crawling dynamic web content presents several challenges because the content is generated on the fly, often in response to user actions. Here are some types of dynamic content that crawlers need to handle:
- **JavaScript-generated content:** Many modern websites use JavaScript to load content asynchronously. A simple crawler that only reads the initial HTML source will miss this content.
- **Content behind forms:** Content that is only accessible after submitting a form (e.g., search results) can be difficult to crawl.
- **Session-based content:** Content that changes based on the user's session (e.g., shopping cart contents) is not suitable for crawling.
- **AJAX-powered pages:** Pages that use AJAX to update content without a full page reload can be tricky to crawl.
- **Infinite scroll:** Pages that load more content as the user scrolls down can cause a crawler to get stuck in a loop.

### b) Briefly explain summarization. List the types of summarization and explain any one in detail.
Summarization is the process of creating a short, accurate, and fluent summary of a longer text document. The goal is to provide the most important information from the original text in a condensed form.

**Types of Summarization:**
1.  **Extractive Summarization:** This method works by selecting a subset of the most important sentences from the original text and combining them to form a summary.
2.  **Abstractive Summarization:** This method involves generating new sentences that capture the meaning of the original text. This is a more advanced technique that requires natural language generation capabilities.

**Extractive Summarization in detail:**
Extractive summarization techniques typically involve the following steps:
1.  **Sentence Segmentation:** The text is broken down into individual sentences.
2.  **Sentence Scoring:** Each sentence is assigned a score based on its importance. This can be done using various features, such as term frequency, sentence position, and the presence of important keywords.
3.  **Sentence Selection:** The sentences with the highest scores are selected to be included in the summary.
4.  **Summary Generation:** The selected sentences are combined in their original order to form the final summary.

### c) State the different approaches to find precise answers in Question Answering.
Question Answering (QA) systems aim to provide direct answers to questions posed in natural language. Here are some approaches to find precise answers:
1.  **Information Retrieval-based QA:** This approach treats the question as a query and retrieves relevant documents. It then uses passage retrieval and answer extraction techniques to find the specific answer within the documents.
2.  **Knowledge-based QA:** This approach uses a structured knowledge base (like a knowledge graph) to find answers. It involves parsing the question to understand its semantic meaning and then querying the knowledge base to retrieve the answer.
3.  **Hybrid QA:** This approach combines both information retrieval and knowledge-based techniques. It might first retrieve relevant documents and then use a knowledge base to verify or refine the answer.
4.  **Deep Learning-based QA:** Modern QA systems often use deep learning models (like transformers) that are trained on large datasets of question-answer pairs. These models can understand the context of the question and generate more accurate and fluent answers.

### d) Discuss Item based collaborative filtering. Provide suitable example.
Item-based collaborative filtering is a recommendation algorithm that recommends items to a user based on the similarity between items. The core idea is that if a user likes a particular item, they are also likely to like similar items.

**How it works:**
1.  **Item-Item Similarity:** The algorithm first builds an item-item similarity matrix. The similarity between two items is calculated based on how users have rated them. For example, if many users who liked item A also liked item B, then A and B are considered similar.
2.  **Prediction:** To make a recommendation for a user, the algorithm looks at the items the user has already rated. It then finds similar items and predicts the user's rating for those items based on their ratings for the similar items.

**Example:**
Imagine a user has watched and liked the movie "Iron Man". To recommend a new movie, the system would look for movies that are similar to "Iron Man". If "The Avengers" is found to be highly similar (because many users who liked "Iron Man" also liked "The Avengers"), the system would recommend "The Avengers" to the user.

### e) Write the challenges and techniques of multilingual retrieval.
Multilingual information retrieval deals with retrieving information from a collection of documents in multiple languages.

**Challenges:**
- **Language Identification:** The system must be able to identify the language of the query and the documents.
- **Cross-Lingual Retrieval:** The query might be in one language and the relevant documents in another.
- **Lexical and Syntactic Differences:** Different languages have different vocabularies, grammar, and sentence structures.
- **Cultural Differences:** The same concept can be expressed differently in different cultures.

**Techniques:**
- **Machine Translation:** Translate the query into the language of the documents, or translate the documents into the language of the query.
- **Cross-Lingual Word Embeddings:** Learn vector representations of words that are aligned across different languages.
- **Cognate Matching:** Identify words that have a common origin and similar spelling in different languages.
- **Dictionary-based Translation:** Use bilingual dictionaries to translate terms between languages.

### f) Elaborate the concept of A/B testing.
A/B testing (also known as split testing) is a method of comparing two versions of a web page or app against each other to determine which one performs better. It is a randomized experiment with two variants, A and B.

**How it works:**
1.  **Create two versions:** Create two different versions of a web page (e.g., with different headlines or button colors). Version A is the control, and version B is the variation.
2.  **Split the traffic:** Randomly show version A to one group of users and version B to another group.
3.  **Measure the results:** Track a specific metric (e.g., click-through rate, conversion rate) for each version.
4.  **Analyze the data:** Compare the performance of the two versions to see which one was more effective.
A/B testing is widely used in web design, marketing, and product development to make data-driven decisions and improve the user experience.

## Q4
### a) What are the challenges of IR?
1.  **Vocabulary Mismatch:** Users may use different words to describe the same concept than what is used in the documents.
2.  **Ambiguity:** Words can have multiple meanings, and the user's intent may not be clear from the query.
3.  **Scalability:** Search engines need to handle massive amounts of data and a high volume of queries.
4.  **Spam:** Web spam (e.g., keyword stuffing) can make it difficult to find relevant information.
5.  **User Satisfaction:** It is challenging to measure and optimize for user satisfaction, as it is a subjective concept.
6.  **Dynamic Content:** The web is constantly changing, and search engines need to keep their index up-to-date.

### b) With the help of an example, elaborate the concept of HITS algorithm.
The Hyperlink-Induced Topic Search (HITS) algorithm is a link analysis algorithm that rates web pages. It was developed by Jon Kleinberg. HITS identifies two types of important pages for a given query:
- **Hubs:** Pages that have many outgoing links to authoritative pages.
- **Authorities:** Pages that have many incoming links from hubs.

**Example:**
Imagine a user searches for "universities". The HITS algorithm would first find a set of relevant pages (the "root set"). It would then expand this set to include pages that link to or are linked from the pages in the root set. In this expanded set, a page that lists many universities (e.g., a university directory) would be considered a good hub. A university's home page, which is linked to by many directories, would be considered a good authority. The algorithm iteratively updates the hub and authority scores of the pages until they converge.

### c) Briefly explain Surveys in information retrieval.
In the context of information retrieval, "surveys" typically refer to survey papers or review articles that provide a comprehensive overview of a particular topic or research area. These surveys are valuable resources for researchers and practitioners because they:
- **Summarize the state of the art:** They review the existing literature and summarize the key findings, techniques, and challenges in a specific area.
- **Identify trends and future directions:** They often identify emerging trends and suggest promising directions for future research.
- **Provide a structured overview:** They organize the literature in a structured way, making it easier for readers to understand the landscape of a research area.
- **Serve as a starting point for new researchers:** They are a good starting point for new researchers who want to get up to speed on a new topic.

### d) Define Boolean model along with a suitable example.
The Boolean model is a classical information retrieval model that is based on Boolean logic. In this model, documents are represented as sets of terms, and queries are expressed as Boolean expressions of terms, using operators like AND, OR, and NOT.

**Example:**
Consider a query "data AND science". A document will be retrieved if and only if it contains both the term "data" and the term "science". A query "data OR science" will retrieve documents that contain either "data" or "science" or both. A query "data AND NOT science" will retrieve documents that contain "data" but not "science".

The Boolean model is simple and easy to implement, but it has some limitations. It does not rank the retrieved documents, and it can be difficult for users to formulate effective Boolean queries.

### e) Write the applications of text categorization.
Text categorization (or text classification) is the task of automatically assigning a document to one or more predefined categories. It has many applications, including:
- **Spam Detection:** Classifying emails as spam or not spam.
- **Sentiment Analysis:** Determining the sentiment (positive, negative, or neutral) of a piece of text, such as a product review or a social media post.
- **Topic Labeling:** Assigning topics to news articles or blog posts.
- **Language Identification:** Identifying the language of a document.
- **Customer Support:** Automatically routing customer support tickets to the appropriate department.

### f) State the different web crawling techniques and explain any one in brief.
**Web Crawling Techniques:**
1.  **Focused Crawling:** A crawler that attempts to download only pages that are relevant to a pre-defined set of topics.
2.  **Distributed Crawling:** Using multiple machines to crawl the web in parallel, which can significantly speed up the crawling process.
3.  **Incremental Crawling:** Periodically re-crawling pages to keep the index up-to-date with changes on the web.
4.  **Deep Web Crawling:** Crawling content that is not accessible through static links, such as content behind forms or in databases.

**Focused Crawling in brief:**
A focused crawler aims to selectively seek out pages that are relevant to a specific topic or set of topics. It uses a classifier to predict the relevance of a page before downloading it. The crawler prioritizes URLs that are likely to lead to relevant pages and avoids crawling irrelevant parts of the web. This can make the crawling process more efficient and effective for specific applications where only a subset of the web is of interest.
