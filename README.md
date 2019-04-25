# TopicSignificanceRank
Based on the information here: [http://qpleple.com/topic-coherence-to-evaluate-topic-models/](http://qpleple.com/topic-coherence-to-evaluate-topic-models/)
Calculating the topic coherence for LDA through sklearn, rather than through Gensim

### Goal
Wanted a method to find Cohernece using sklearn, rather than rely on the *Gensim* model or be stuck using Perplexity or Log-Likliehood as built into sklearn's [sklearn.decomposition.LatentDirichletAllocation](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.LatentDirichletAllocation.html) model.

### Writng the Code
Used [this website](http://qpleple.com/topic-coherence-to-evaluate-topic-models/) to make the various calculations.  Note that *UCI* seems to be based on an external corpus, which is not how this was developed or tested.

### Testing the Code
Based on [this website](https://www.machinelearningplus.com/nlp/topic-modeling-python-sklearn-examples/), I've processed the Newsgroup dataset the same way they did, used the same [CountVectorizer](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.CountVectorizer.html), and then ran my *TopicCoherence* class on the resulting vocabulary.
Ran the same [gridsearch](https://www.machinelearningplus.com/nlp/topic-modeling-python-sklearn-examples/#11howtogridsearchthebestldamodel) they did.  They got 10 as the best (using perplexity).  According to [sklearn](https://scikit-learn.org/0.19/datasets/twenty_newsgroups.html), there *should* be 20 topics.

I got 25 topics.  This may be partially due to the issues with UCI (see below).  Overall, still better than *perplexity*

### Using This
Though it was not specified [here](http://qpleple.com/topic-coherence-to-evaluate-topic-models/), other sources seem to indicate that *UCI* is based on a different corpus than the one in question, so keep this in mind.  UMASS is based on the corpus itself.  It is recommended to use one or the other (I have used UMASS in actual practice).