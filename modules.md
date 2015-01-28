---
layout: page
title: "Technical overview"
description: "Technical overview of Platypus"
group: navigation
---
{% include JB/setup %}


The PPP framework is based on a modular approach. The input
is passed from the user interface to a core that distributes it between modules. Each module
can do whatever it wants to simplify the input or solve it partially. This operation is
repeated as long as there are improvements in the results. Then, the core returns these
results and the user interface displays them to the user.

The PPP has been designed in order to allow everyone to implement its own module (astronomy module, cooking module...)
and connect it easily to our project. [A tutorial](//github.com/ProjetPP/Documentation/blob/master/getting-started.md) is provided.

Here is a partial overview of the current structure:

[![PPP structure](structurePPP2.png "The modular structure of the PPP")](structurePPP2.png)

The communication between modules are done in a standardized way. The specifications are provided
in the [Documentation repository](//github.com/ProjetPP/Documentation).


## Current modules

Basic information about the main modules currently available:

### [Core](//github.com/ProjetPP/PPP-core)

The main module of the *PPP* infrastructure. Coordinates the work of the other modules.

### User interfaces

#### [Web user interface](https://github.com/ProjetPP/PPP-WebUi)

A single page web application used as main user interface of the Platypus demo.

### Question Parsing

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

### Other modules

#### [Wikidata](https://github.com/ProjetPP/PPP-Wikidata)

Answers general knowledge question, using the data stored in [Wikidata](http://www.wikidata.org/) and [Wikipedia](http://www.wikipedia.org/).

Uses the *Wikidata API*, the *WikidataQuery API* and the *Wikipedia API*.

#### [Computer Algebra System](https://github.com/ProjetPP/PPP-CAS)

Answers mathematical queries.

Uses *Simpy* and *Ply*.

#### [Spell Checker](https://github.com/ProjetPP/PPP-Spell-Checker)

Performs spell-checking on the input sentence.

Uses the *Aspell API*.

#### [Integer sequences](https://github.com/ProjetPP/PPP-OEIS)

Answer to queries related to integer sequences: identify them and give the
following integers.

Uses the *OEIS API*.

#### [Logging backend](https://github.com/ProjetPP/PPP-Logger)

Logging of the questions, to help developers to enhance their modules.



## Documentation

### Internal documents

####[Technical documentation](https://github.com/ProjetPP/Documentation)

Getting started document and data model and module communication specifications.

####[Literature review](documentation/pppLiteratureReview_YassineHamoudi.pdf)

How to answer questions in natural language using existing structured databases?


### ENS project documents (outdated)

####[Final report](documentation/finalReport.pdf)

Published on December the 20th, 2014.

Detailed presentation of the project after three months of work (end of the school semester).

####[Public presentation](documentation/publicPresentation.pdf)

Published on December the 18th, 2014.

Slides of the presentation held at the *ENS Lyon* on December 18th, 2014.

####[Midterm report](documentation/midtermReport.pdf)

Published on November the 4th, 2014.

Presentation of our achievements after one month and a half of work (half of the school semester).

####[Project proposal](documentation/proposal.pdf)

Published on October the 3rd, 2014.

Presentation of what we intended to do at the beginning of the project.

