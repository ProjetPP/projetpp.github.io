---
layout: page
title: "Modules"
description: "Modules of the PPP"
group: navigation
---
{% include JB/setup %}

Our project is based on a modular approach. The input question is passed to a core that distributes it between modules. Each module can do whatever he wants to simplify the input or solve it partially. The core decides which modules are the most relevant.

Our goal is to allow everyone to implement its own module (astronomy module, cooking module...) and connect it easily to our project. For a more detailed overview, please have a look at the [midterm report](midtermReport.pdf).

Basic informations about the main modules currently available:

## Question Parsing

The goal of these modules is to transform questions into trees of triples.

For instance, the question "What is the birth date of the president of France?"
would be transformed into the triple `((France, president, ?), birth date, ?)`.

#### [Grammatical](//github.com/ProjetPP/PPP-QuestionParsing-Grammatical)

Produces trees of triples with a grammatical approach: we focus on the grammatical
dependencies that exist between words.

Uses the [Stanford CoreNLP](http://nlp.stanford.edu/software/corenlp.shtml) and
the [NLTK](http://www.nltk.org/) libraries.

#### [Machine Learning - Reformulation](//github.com/ProjetPP/PPP-QuestionParsing-ML-Reformulation)

Reformulates the triples produced by the Grammatical module, to obtain triples
which are closer of what is expected by the Wikidata module.

#### [Machine Learning - Standalone](//github.com/ProjetPP/PPP-QuestionParsing-ML-Standalone)

Produces triples from scratch, without any grammatical library.

## Other modules

#### [Wikidata](https://github.com/ProjetPP/PPP-Wikidata)

Answers general knowledge question, using the data stored in [Wikidata](http://www.wikidata.org/) and [Wikipedia](http://www.wikipedia.org/).

Uses the *Wikidata API* and the *WikidataQuery API*.

#### [Computer Algebra System](https://github.com/ProjetPP/PPP-CAS)

Answers mathematical queries. 

Uses *Simpy* and *Ply*.

#### [Spell Checker](https://github.com/ProjetPP/PPP-Spell-Checker)

Performs spell-checking on the input sentence. 

Uses the *Aspell API*.

#### [Web User Interface](https://github.com/ProjetPP/PPP-WebUi)

Communication between the user and the core.

#### [Logging backend](https://github.com/ProjetPP/PPP-Logger)

Logging of the questions, to help developers to enhance their modules.
