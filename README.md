<div align="center">

```mermaid
mindmap
  root((Word2Vec))
    Goal
      Convert words into vectors
      Capture semantic relationships

    Models
      CBOW
        Context predicts target
        Faster
      Skip-gram
        Target predicts context
        Better for rare words

    Training
      Text corpus
      Context window
      Negative sampling
      Hierarchical softmax

    Output
      Static word embeddings
      Similar words have nearby vectors
      Word analogies

    Applications
      Classification
      Search
      Clustering
      NLP feature extraction

    Advantages
      Simple
      Efficient
      Scalable

    Limitations
      One vector per word
      Out-of-vocabulary words
      Cannot capture changing context

    Extensions
      FastText
      Doc2Vec
      BERT
```

# **`Awesome`** [Word2vec](https://wikipedia.org/wiki/Word2vec) [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
</div>

[![YouTube](https://img.shields.io/badge/YouTube-%23FF0000.svg?style=for-the-badge&logo=YouTube&logoColor=white)]() 
[![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)]()

<p align="center">
    <a href="https://github.com/cybersecurity-dev/"><img height="25" src="https://github.com/cybersecurity-dev/cybersecurity-dev/blob/main/assets/github.svg" alt="GitHub"></a>
    &nbsp;
    <a href="https://www.youtube.com/@CyberThreatDefense"><img height="25" src="https://github.com/cybersecurity-dev/cybersecurity-dev/blob/main/assets/youtube.svg" alt="YouTube"></a>
    &nbsp;
    <a href="https://cyberthreatdefence.com/my_awesome_lists"><img height="20" src="https://github.com/cybersecurity-dev/cybersecurity-dev/blob/main/assets/blog.svg" alt="My Awesome Lists"></a>
    <img src="https://github.com/cybersecurity-dev/cybersecurity-dev/blob/main/assets/bar.gif">
</p>

```mermaid
flowchart TB
    T[Text Representation] --> TF[TF-IDF]
    T --> W[Word2Vec]

    TF --> TF1[Calculate term frequency]
    TF1 --> TF2[Calculate inverse document frequency]
    TF2 --> TF3[Create sparse vectors]
    TF3 --> TF4[Measure term importance]

    W --> WV[Create dense word vectors]
    WV --> C[CBOW]
    WV --> S[Skip-gram]

    C --> C1[Context words]
    C1 --> C2[Predict target word]
    C2 --> C3["the cat ___ the mat → sat"]

    S --> S1[Target word]
    S1 --> S2[Predict context words]
    S2 --> S3["sat → cat, on"]

    TF4 --> A[Text Classification]
    C3 --> A
    S3 --> A

    style TF fill:#fef3c7,stroke:#d97706,stroke-width:2px
    style W fill:#ede9fe,stroke:#7c3aed,stroke-width:2px
    style C fill:#dbeafe,stroke:#2563eb,stroke-width:2px
    style S fill:#dcfce7,stroke:#16a34a,stroke-width:2px
    style A fill:#fce7f3,stroke:#db2777,stroke-width:2px
```

## 📖 Contents
- [CBOW](#continuous-bag-of-words-cbow)
- [Skip-gram](#skip-gram)
- [My Other Awesome Lists](#my-other-awesome-lists)
- [Contributing](#contributing)
- [Contributors](#contributors)


## Continuous [bag-of-words](https://wikipedia.org/wiki/Bag-of-words_model) ([CBOW](https://www.tensorflow.org/text/tutorials/word2vec))

<details>
<summary>CBOW Flowchart</summary>
 
```mermaid
flowchart LR
 subgraph Input["INPUT"]
        A1["w(t-2)"]
        A2["w(t-1)"]
        A3["w(t+1)"]
        A4["w(t+2)"]
  end
 subgraph Projection["PROJECTION"]
        SUM["SUM"]
  end
 subgraph Output["OUTPUT"]
        OUT["w(t)"]
  end
    A1 --> SUM
    A2 --> SUM
    A3 --> SUM
    A4 --> SUM
    SUM --> OUT

    style Input color:#000000,fill:#FFF9C4
    style Projection color:#000000,fill:#BBDEFB
    style Output color:#000000,fill:#FFCDD2
```
</details>

---
---

```mermaid
flowchart LR
    W[Word2Vec] --> C[CBOW]
    W --> S[Skip-gram]

    C --> C1[Multiple context words]
    C1 --> C2[Predict one target word]
    C2 --> C3["Example: the cat ___ the mat → sat"]
    C3 --> C4[Faster; strong for frequent words]

    S --> S1[One target word]
    S1 --> S2[Predict surrounding context]
    S2 --> S3["Example: sat → cat, on"]
    S3 --> S4[Slower; strong for rare words]

    style C fill:#dbeafe,stroke:#2563eb
    style S fill:#dcfce7,stroke:#16a34a
```

## [Skip-gram](https://radimrehurek.com/gensim/models/word2vec.html)

<details>
<summary>Skip-gram Flowchart</summary>

```mermaid
flowchart LR
 subgraph INPUT["INPUT"]
        x_wt["w(t)"]
  end
 subgraph PROJECTION["PROJECTION"]
        x_proj["Projection"]
  end
 subgraph OUTPUT["OUTPUT"]
        x_wtm2["w(t-2)"]
        x_wtm1["w(t-1)"]
        x_wtp1["w(t+1)"]
        x_wtp2["w(t+2)"]
  end
    x_wt --> x_proj
    x_proj --> x_wtm2 & x_wtm1 & x_wtp1 & x_wtp2
    classDef label fill:none,stroke:none,color:#666
    style PROJECTION fill:#BBDEFB,color:#000000
    style INPUT color:#000000,fill:#FFF9C4
    style OUTPUT fill:#FFCDD2,color:#000000
```
</details>


##

### My Other Awesome Lists
You can access the my other awesome lists [here](https://cyberthreatdefence.com/my_awesome_lists)

### Contributing
[Contributions of any kind welcome, just follow the guidelines](contributing.md)!

### Contributors
[Thanks goes to these contributors](https://github.com/cybersecurity-dev/awesome-word2vec/graphs/contributors)!

### License
[![CC0](http://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](http://creativecommons.org/publicdomain/zero/1.0)

[🔼 Back to top](#awesome-word2vec-)
