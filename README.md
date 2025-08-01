# 📚 WikiSearchEngine: A Java Web Crawler with TF-IDF & Cosine Similarity

This Java application crawls Wikipedia pages starting from two predefined URLs, builds an **inverted index**, and allows querying the crawled content using **TF-IDF** and **cosine similarity** ranking.

---

## 🚀 Features

- 🔗 Crawls up to **20 distinct Wikipedia pages** starting from two given seed URLs.
- 🧹 Extracts and **cleans textual content**, then builds an inverted index (term ➝ [docID, frequency]).
- 📊 Computes **TF-IDF scores** for terms in each document.
- 🔍 Accepts a **user query**, applies the same TF-IDF weighting, and computes **cosine similarity** with each document.
- 🏆 Returns the **Top 10 most relevant documents** sorted by similarity score.

---

## 🔧 Technologies

- **Java 8+**
- **Maven**
- **[Jsoup](https://jsoup.org/)** for HTML parsing

---

## 🗂️ Project Structure

```
webcrawler-tfidf/
├── pom.xml                         # Project dependencies (Jsoup)
├── README.md                       # Project overview and instructions
├── report/
│   └── Report.pdf                  # Design & explanation
├── src/
│   └── main/
│       └── java/
│           └── com/
│               └── tfidf/
│                   ├── Main.java
│                   ├── crawler/
│                   │   └── WebCrawler.java
│                   ├── text/
│                   │   └── Normalizer.java
│                   ├── index/
│                   │   ├── InvertedIndex.java
│                   │   └── Posting.java
│                   ├── ranking/
│                   │   ├── TFIDFCalculator.java
│                   │   ├── CosineSimilarity.java
│                   │   ├── DocumentTFIDF.java
│                   │   └── Ranker.java
```

---

## 👥 Team Responsibilities

| Module                       | Description                                                         | Team Members         |
|-----------------------------|---------------------------------------------------------------------|----------------------|
| Web Crawling                | Crawl Wikipedia, avoid duplicates, restrict domain                 | Amany, Israa         |
| Text Normalization & Index  | Tokenization, normalization, inverted index construction           | Joseph, Yousef       |
| TF-IDF & Ranking            | Compute TF-IDF weights, cosine similarity, and rank documents      | Salma, Jonathan      |
| Documentation & Comments    | Code documentation, final report                                   | Whole Team           |

---

## 🛠️ How to Run the Program

### 🧱 Prerequisites

- Java 8 or later
- Maven installed

### 📦 Setup and Build

1. Clone the repository:
   ```bash
   git clone https://github.com/IsraaXx/WikiSearchEngine.git
   cd WikiSearchEngine
   ```

2. Add **Jsoup** dependency to `pom.xml`:
   ```xml
   <dependency>
       <groupId>org.jsoup</groupId>
       <artifactId>jsoup</artifactId>
       <version>1.15.3</version>
   </dependency>
   ```

3. Build and run:
   ```bash
   mvn clean install
   mvn exec:java -Dexec.mainClass="com.tfidf.Main"
   ```

4. When prompted, **enter your search query** and get ranked results based on relevance.

---

## 📑 Deliverables

- ✅ Fully working Java application with crawling, indexing, and search functionality.
- 📄 Report explaining the design of each module.
- ❌ No need for extra user manual or presentation files.

---

## 🧠 Concepts Used

- **Web Crawling** with domain restrictions and deduplication.
- **Text Normalization** (tokenization, case folding).
- **Inverted Index** structure.
- **TF-IDF Weighting**:
  - TF = 1 + log10(term frequency)
  - IDF = log10(N / df(term))
- **Cosine Similarity** to compare the user query with document vectors.

---

## 💡 Example Query Flow

```
User enters: ancient egypt king
→ Query vector computed
→ Cosine similarity calculated with each of the 10 documents
→ Top 10 relevant Wikipedia pages printed (ranked)
```

---

## 🧪 Testing Tips

- Use sample queries like: `pharaoh`, `egypt`, `dynasty`, `history`.
- Check if duplicate Wikipedia pages are skipped during crawling.
- Validate inverted index by printing terms and posting lists.

---

## 📬 Contact

This project was built as part of **Assignment 2 - Web Crawler with TF-IDF** at Cairo University.

---

> 💬 “The best search engine is the one you build yourself.”
