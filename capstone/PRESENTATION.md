# Capstone presentation guide

Each team presents its project in **8 minutes**, followed by questions. The presentation must show what was built, which parts of the course it relies on, the data, the organization of the code, how it was coded, and a live demonstration of the application.

The guide applies to every topic. The headings of the presentation are fixed; the content depends on the project.

## Format

| Item | Rule |
|------|------|
| Duration | 8 minutes of presentation and demo, then questions |
| Speakers | Every member speaks, for a similar amount of time |
| Support | No document is required: the presentation is oral and relies on the repository and the application (see [What is shown](#what-is-shown)) |
| Demo | Live, on the team's own laptop or on the published application. A recorded backup is kept ready |
| Version | The repository as it is at the start of the session is the version that is presented |
| Questions | Asked to a member chosen by the teacher, on any part of the project |

## Structure and time budget

| # | Part | Time |
|---|------|------|
| 1 | Context and goal | 0:45 |
| 2 | Course concepts used | 0:45 |
| 3 | Data | 1:00 |
| 4 | Code organization | 1:00 |
| 5 | How it was built, results | 2:00 |
| 6 | Demo | 2:00 |
| 7 | Limits and conclusion | 0:30 |

Rehearse with a timer. A presentation that exceeds the time is stopped at 8 minutes, and the demo is the part that suffers.

### 1. Context and goal

- The problem in one sentence, and who has it (a person with a name and a situation is better than "users").
- What the application does: input, output, one example.
- Why an NLP approach is relevant, and what the existing alternative is (manual work, keyword search, nothing).

### 2. Course concepts used

State precisely which parts of the course are used, and for each one what was chosen, why, and what was considered instead. The table lists the possible parts; a project rarely uses all of them.

| Course part | Examples of elements to name |
|-------------|------------------------------|
| Text preprocessing | Regular expressions, tokenization, lemmatization or stemming, stop words, handling of emojis, URLs, accents, other alphabets |
| Text representation | Bag of Words, TF-IDF, n-grams, Word2Vec, GloVe, sentence embeddings |
| Core NLP tasks | Classification, sentiment analysis, topic modeling, named entity recognition, similarity and search |
| Deep learning and LLMs | RNN, LSTM, GRU, transformers, pre-trained models, prompting, retrieval-augmented generation, LLM API |

A short sentence per choice is enough: "TF-IDF with bigrams, because the texts are short and the vocabulary is specific; sentence embeddings were tested and gave a lower score on this data."

### 3. Data

- **Source**: name, link, license or terms of use; if the data was collected, how and when.
- **Content**: number of documents, language(s), length of a typical document, labels and their distribution. One or two real examples shown.
- **Preparation**: what was removed or corrected, what was kept and why, how the training and test sets were built.
- **Limits**: missing categories, imbalance, period covered, languages or groups that are over- or under-represented, risks of bias.

### 4. Code organization

Show the structure of the repository and explain the role of each folder or file in a few words. A typical structure:

```
nlp-capstone-<team>/
├── README.md              problem, data, results, how to run, who did what
├── pyproject.toml         or requirements.txt: dependencies
├── data/                  small samples and a script that downloads the full data
├── notebooks/
│   ├── 01_exploration.ipynb
│   ├── 02_modeling.ipynb
│   └── 03_evaluation.ipynb
├── src/                   functions reused by the notebooks and by the application
│   ├── preprocessing.py
│   └── model.py
└── app.py                 the web interface
```

The structure is presented on screen, in the file explorer or in the `README.md`, and answers three questions: where is the data and how is it obtained, where is the logic, and what command starts the application. Every member can say who wrote which part.

### 5. How it was built, and results

This is the technical core of the presentation.

- **Pipeline**: a diagram with the steps from the raw input to the output of the application (cleaning, representation, model, post-processing, interface).
- **Code**: one or two short extracts of the central function, shown on screen and explained line by line. Whoever presents an extract must be able to modify it.
- **Choices and attempts**: what was tried, what did not work, what was changed as a result.
- **Evaluation**: the metric and why it fits the problem, the score of a simple baseline, the score of the final approach, in a small table. If an LLM is compared with a classical model, the cost and the response time are mentioned.
- **Error analysis**: two or three real examples where the system fails, with an explanation.
- **Use of AI assistants**: what they were used for, which suggestions were rejected or corrected, and how the results were checked.

### 6. Demo

The demo shows the application running, not a screen recording of a notebook. It follows a script written in advance:

1. a typical input, with an expected result;
2. a more difficult input (long, noisy, in another language, ambiguous);
3. an input where the application fails, and a short explanation of the failure.

Preparation:

- the application is started and tested before the session; models and data are downloaded in advance, so that nothing depends on the network;
- the three inputs are prepared in a text file, to copy and paste;
- the course LLM key expires after one day: it is checked on the morning of the session, or the demo uses a recorded response as a fallback;
- a screen recording of the full demo, one minute long, is available in case of a technical problem. It is shown only if the live demo fails.

### 7. Limits and conclusion

- Two limits of the project, stated plainly, and what would be done with more time (more data, another model, a user test).
- One sentence on what the team learned.

## What is shown

No slides or other document have to be produced. The presentation is oral and relies on what already exists: the repository (`README.md`, folder structure, notebooks), the code and the running application. Slides can be used if the team finds them useful, but they are not expected and are not assessed.

Good practice, whatever is shown:

- one message at a time, with few words;
- figures and tables readable from the back of the room: large text, labeled axes;
- code extracts of 15 lines at most, with the important lines highlighted or commented;
- everything needed (README, notebooks, application, data) is open and tested before the session starts, so that no time is lost looking for a file.

## Questions

Questions can be asked to any member, on any part. Examples:

- Why this representation and not another one? What was the score of the alternative?
- What does this line do? What happens if this parameter changes?
- What does the application do with a word it has never seen?
- How was the test set built? Could the same document be in the training set and in the test set?
- Which part of the code was written with an AI assistant, and how was it checked?
- What would change if the data were ten times larger, or in another language?

A short and honest answer ("this was not tested") is better than an invented one.

## Link with the grading

| Part of the presentation | Criterion of the grid (see [README](README.md)) |
|--------------------------|--------------------------------------------------|
| Context, data | Problem and data (4) |
| Course concepts, how it was built, results | NLP pipeline (6) |
| Demo | Working application (5) |
| Structure, time, limits, answers to questions | Presentation and understanding (5) |

## Checklist before the session

- [ ] The repository is public, the `README.md` explains how to run the application, and no key is committed.
- [ ] The application starts from a clean clone with the documented commands.
- [ ] The README, the notebooks and the application are open and ready, and the timing is rehearsed.
- [ ] The demo script, the three inputs and the recorded backup are ready.
- [ ] The data, the models and the LLM key (if used) are available without relying on the network or on a download.
- [ ] Each member can explain every part of the project, including the code written with an AI assistant.
