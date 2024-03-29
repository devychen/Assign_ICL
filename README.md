# Assign_ICL

Grade: 1.3 結課大吉！(23 Feb 2024)

[Regex practice](https://regexr.com/) <br>

### Section1. CL and Definition

1. **Definition of Computational Linguistics**  
Brings computer and languages together. The specific study of language from a computational perspective. The study of of computer systems for understanding and generating natural language.
2. **Aims of the field**: To get computers to perform human language tasks.
3. **Different characteristics and applications**  
Sentimen analysis, dialogue system, speech recognition, machine translation, etc.
4. **Different perspectives (theory, methods, tasks)**  
- _**Theory**_: Describing content and format of descriptions of phenomena, including formulating abstract models/frameworks to understand underlying pricinciples governing language structures and behaviours. _Understanding_
- _**Methods**_: Developing tools, procedures, formalism to facilitate NLP/ML by creating algorithms/models. _Modeling_
- _**Tasks**_: applying methods to solve specific language tasks. _Utilising_
5. **Different methodologies (rule-based, statistical approaches)**  
- _**Rule-based** approaches_: Explicitly model language by defining set of linguistic rules and structures crafted by human experts. Reply on predefined sets of linguisitcs rule. Transparent, interpretable, but labour-intensive and struggle from complexity.
- _**Statistical** approaches_: Implicitly model language based on patterns and probabilities derived from large datasets, leaveraging statisitcal models and ML algorithms to learn these patterns. Handles complexity, struggle from limited training data.
- _How language is related to this_: Language is rule-govened yet shows statistical regularities. Rule-based capture explicit linguistic features, statistical embrace implicit statistical patterns. The interplay between them reflects the multidimensional nature of language in computational modeling.
6. **Relation to General Linguistics**
- GL is the study of human language as a universal and recognasible part of human behaviours and cognitive abilities.
- Common foundation in exploration of language
- Approches and Outlook: GL looks at all languages' universals and principles, CL deals more specifically with the technological aspects of language processing. GL covers entirety of human languages. CL focuses on pratical applications and the development. GL - theoretical foundations, CL - real application.
- CL can be viewed as an applied subset of GL, theoretical insights from the latter guide the CL models for practical language-specific tassks. Altogther contribute to our understanding of language.
7. **Main subtasks in NLP (NLU, NLG)** 
- _**NLU**nderstanding_: mapping given NL input into useful representations, analysing different aspects of the input: lexicon (POS tagging), morphology (lemmatization), syntax (dependency parsing), discourse (anaphora resolution), pragmatics (sentiment detection).
  - Current applications: Virtual assistant, understand user queries, sentiment analysis
- _**NLG**eneration_: producing meaning natural language text from some more abstract representation: subtle (difficult to get it right), very domain-specific (systems are tailored to particular applications/tasks: e.g. generating weather reports vs. poems).
  - Current application: Virtual assistant to response



### Section 2. Encoding Language

**What is language**
A structured system of communication that consists of grammar and vocabulary. Can be described with regards to phonetics, phonology, morphology, syntax, semantics, and pragmatics. <br>
Writing is not universal while language is. Writing is used to represent language not language itself.
1. **Writing Systems**
- Definion: A system of more or less permanent marks used to represent an utterance in such a way that it can be recovered more or less exactly without the intervention of the utterer. (My: A system of making permanent marks to represent spoken words so it can be recovered almost exactly without involving the speaker to be there.)
- Three types:
  - **_Alphabetic_**: Each character/letter represents a single sound/phoneme. Ideally has a one-to-one sound-letter/char correspondence, but multiple-one also observed. Semantic meanings not captured by or varied between letters. In this system, characters could represent all sounds (vowels and consonants) as in English, IPA, or in some cases consonants only (also called **_Abjads_**) such as in Hebrew, Arabic.
  - **_Syllabic_**: Each character/symbol represents a whole syllable. Two variants: **abugida** (each family shares a common consonant but varies in vowels. Example: Burmese), **syllabary** system (each syllable has a unique symbol but without systematic organisation. Example: Japanese). This system focuses on phenetic properties instead of semantic ones, esp. on syllabic sound patterns.
  - **_Logographic_**: Each character/symbol represents an entire word/morpheme and carries a specific meaning. Example: Chinese. This system priortises semantics over phonetics, characters has a direct representation of semantic content.
    - A logograph: a symbol represents a unity of meaning (as opposed to a unit of sound - phoneme).
  - **_Hybrid_**: Combines elements of different systems. Individual alphabetic chars could form the syllabic characters togther. Example: Korean, which has a blend of all three (alphabetic, syllabic, logographic) elements. This system keeps a balance and flexibility of phonetic and semantic properties.
  - * **_Emojis_** are not a writing system as they do not represents sound/meaning pairings in any language but emotions.
2. **How is language encoded on computers? (bits & bytes)**  
-  Information on computer is stored in bits, in the context of writing systems, a particular character will have a unique pattern of numbers represented by bit sequences. With 8 bits (a single byte) and each byte storing a separate character, we then can represent $2^8$ characters.
3. **Binary and Hexadecimal System**
- Binary system (2 digits. Decimal - $1 10 10^2$), using 0 and 1. Leftmost bit being the most significant (Big Endian notation)
  - Binary to decimal: 01101 = $0 * 2^4 + 1 * 2^3 + 1 * 2^2 + 0 * 2^1 + 1 * 2^0 = 13$
  - Decimal to binary (Check remainders):  $9/2 = 4$ ...%1; $4/2 = 2$ ...%0; $2/2 = 1$ ...%0; $1/2 = 0$ ...%1
- Hexadecimal system (16 digits), using 0 ～ 9 and the letters A (=10) to F(=15).
-   0xA8E = $10 * 16^2 + 8 * 16^1 + 14 * 16^0 = 2702$ Ox is just a prefix for hexadecimal.
- Conversion: 4 positions in binary can be represented with 1 position in hexadecimal 
4. **ASCII**
- ASCII uses 8 bits to store 256 characters, was developed for the Latin Alphabet (esp. English)
- Served as basis for future encoding systems
- You should be able to read and use the ASCII chart You should be able to discuss the necessity of a standardised coding table & the limitations of ASCII 
5. **Unicode**
- Uses (up to) 32 bits
- has a single representation for every character UTF-8 allows for backwards compatibility with ASCII
- UTF-8 allows for variable length (first bits show how many bytes are used)
  - 0 ... → one byte
  - 110... → two bytes (following: 10..) ... 
- You should be able to discuss the advantages and limitations of unicode


### Section 3. Writers' Aids 

1. **Spelling variation** (regional differences, different genres)
2. **Spelling error types** (non-word, real-word errors)
3. **Error sources** (opaque writing systems, L1 transfer, etc.)
4. **Basic edit operations** (I, D, S, T)
5. **High-level stages** in method for automatic spell checking (detection, generation, ranking). Information sources for different stages:
- Detection: word lists
- Generation: a) rules b) list of valid words & similarity measures
- Ranking: explain why ranking is needed 
6. **Minimal String Edit Distance** (concept and algorithm)
7. **Operatilising string similarity** with naive examples
8. **Modelling string similarity** after human typist operations
9. **Why DAGs are useful tool** for representing search space 


### Section 4. Text as Data

1. **What is a Corpus?**
- Structured collection of texts collected with a specific question in mind. Usually contains linguistic annotation and metadata 
2. **What is Metadata?**
- Data describing the primary, ra data (creation date, information and the speaker/writer/author, tags, ...) 
3. **What are Linguistic Annotation**
- POS tags
- Sentence/word boundaries
- Parse trees, ...
- **TTR** = #types #tokens 
4. **Limitations & applications** of corpora 
5. You should be able to discuss:
- Whether a certain corpus is **appropriate** for a specific research question
- What would be **the steps to collect data**
- What kind of (meta) data would be necessary to answer a certain RQ... 



### Section 5. Text Classification

1. **How computers learn**
2. **Feature vectors**
3. **Training, Testing, Validation Set**
4. **Supervised vs. Unsupervised ML**
- Supervised: Labeled data through expert annotators. 
  1) Split the data
  2) Train the model
  3) Test and cross-validate
  4) Evaluate 
- Unsupervised: 
  1) Feature extraction
  2) Apply algorithm on dataset
  3) Inspect resulting structure 
5. **How to evaluate a model** 
- Recall
- Precision
- Accuracy
- TNR
- How are these calculated?
- When should you use which measure?
  - Is it more important to catch everyone with the disease and maybe treat healthy patients, or is it better to miss some patients but be sure not to treat healthy people? Is it better to censor non-harmful tweets and make sure to censor every hate speech tweet ... ? 
4. **NLP segmentation**
- Preprocessing
- Tokenisation
  - What is a token
  - What are the challenges (contracted forms, hyphenated forms, periods (St.), special characters, NER, …)
- Sentence segmentation:
  - How are sentences defined
  - What are the challenges in sentence segmentation (esp. with regards to other languages than English)



### Section 6. ASR

1. Brief introduction to **speech** (phones and phonemes, vocal tract)
2. **How speech is represented with computers**
3. Different **speech processing applications**
- Which ones can you think of?
- What task does each one perform?
- What language technology components are required in the pipeline to make these applications work?
4. **Automatic speech recognition**
5. **Inputs/Outputs**
6. **Why ASR is a difficult problem**
7. **Noisy channel model** and **application to ASR**
8. **System architecture** of ‘classical’ ASR system. Role of components:
- Acoustic model
- Lexicon
- Language model
- Search lattice
- Decoder
9. **Purpose of language model**
- Using a language model to rank different candidates (“wooden boats”)
- A very high-level look at probabilities (coin flipping) and n-gram language models
10. **Steps in training a speech recogniser**
- Dataset requirements, feature extraction, training, testing, evaluation, error analysis



### S7 Text Search

1. Why search can be challenging, with example(s)
2. Different search tasks (hint: Google, Quora, Netflix)
3. Key terms:
- **Information need**
- **Intent**
- **Query**
4. **Formulating querie**s: general user vs. specialist user
5. **Regular expression**
- Definition 
- Basic building blocks:
  - Literals
  - Wild cards
  - Escaping
  - Modes (/g, or /i)
  - Character sets and ranges
  - Quantified repetition
  - Groups using parentheses
  - Anchors
6. **Multiple Documents**
- Examples of applications searching multiple documents
- What document indexing is, why it is important, and different approaches (term-by-document matrix, inverted indices list)
7. **Evaluating search quality**
- User experience surveys
- Objective user interaction logs
- Precision, Recall (and challenges with computing recall), F-measure
8. An understanding of the **limitations of these measures** in the context of Text Search
9. An understanding of **why Ranking is important in text search**



### Section 8. CALL

1. Characteristics of learner language (in contrast to native-like language) and implications for NLP technology
2. Know what an Intelligent Tutoring System (ITS) is
3. Be able to talk about NLP applications in the context of ITS for language learning
4. NLP applied to well-formed language (e.g. FLAIR)
5. NLP applied to malformed learner language <br>
For each, be able to describe:
- The needs of the users (e.g., input, corrective feedback)
- How NLP can be used in an ITS to meet those needs
- Using knowledge from other lectures (e.g. text search), make suggestions for how to evaluate the quality of an NLP-enhanced ITS system


### Section 9. Dialogue Systems


1. Terminology: Speech acts, common ground, turn taking, adjacency pairs
- How are these important for dialogue systems?
2. Grice’s Maxims
- What are they
- how are they defined?
- Why are they important in dialogue systems? What happens if they are not met?
3. Task Specific Systems
Designed to help accomplish one or more specific tasks
4. Intents containing slots, intent recognition
5. Independent Systems
6. Chatbots
7. Different implementations (brute force, rule-based, corpus trained, generative)
- You should be able to explain the previously mentioned phenomena on chatbot examples (e.g. explain the rule based approach on the example of ELIZA)
How are chatbots evaluated? (Turing test, Winograd Schemas)
8. POS tagging
Information on word type (noun, verb, etc)
9. Different granularity depending on corpus
- Used to encode morphological and syntactical information of tokens
- Can be used to measure linguistic properties such as complexity o pronunciation
- Often prerequisite for other NLP tasks
10. Methods for POS tagging
- Rule-based
  - Use constraint grammars and lexicons to retrieved all candidate POS tags and the associated rules
  - They each rule on input sentence and exclude POS tag if tule does not fit
- Statistical
  - Input a token sequence, assign a POS tag to each token, handle ambiguity by exploring different possible sequences
  - Rank each sequence by its statical probability using supervised ML
- Challenges in POS tagging
  - Ambiguity: Sometimes, various POS tags are possible (I can can a can of tuna) - context necessary
- You should be able to annotate short sequences and discuss possible ambiguities including ways to resolve the ambiguity
11. Parsing
- Represent grammatical structures or relationships
- Constituency Parsing
  - Constituents: Group of words forming syntactic units (e.g. NPs)
  - Parsing assigns syntactic structures
  - - Identification of multi-word units and nested structures
- Visualisations: Trees and parentheses notation. You should be able to read & create both forms
- Challenge: Ambiguities, e.g. I saw the man with the telescope
- Dependency Parsing
  - Aim: Capture the syntactic relations between words in a sentences using directed grammatical relation between pairs of words
  - Relation have governor (head) and dependent
  - Challenges: Attachment and corrpdinasion ambiguity



### S10 LLMs

1. Technical Aspects
- You do not need to be able to explain what neural networks are or what a transformer is, but you need to know the vocabulary!
- You should be able to discuss what was new about LLMs (one model for all, parallelisation, attention)
2. Large Language models
3. Applications of LLMs
- You should be able to name a few applications of LLMs
4. Ethical Aspects
- Bias
- Difficulty of unbalanced, restricted, and biased corpora
- How are social biases inscribed in the data?
- Why is this problematic?
- Fine tuning
- Why is it difficult to ensure that only ‘ethical’ utterances are generated?
- How did chatbots try to solve this problem? How is it done nowadays?
5. Environment impact
- You should be able to shortly discuss possible environmental impacts (also considering the large datasets, long learning etc.)




