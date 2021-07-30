This README describes the various files created for 2021S1 COMP90049 Project 3.

There are various files in these archives: other than this README, each one can be identified by its filename, in the format {set}_{type}.{filetype}
- {set} refers to either train, dev, or test:
    train: You should use this data when building a model
    dev: You should use this data when evaluating a model
    test: You should submit the outputs on this data to Kaggle; the labels are not given
   
- {type} refers to either full, count, tfidf, glove300:
    full: This contains the raw text of the corresponding tweets, one tweet per line, in the following format:
          region,user,tweet (newline)
          where region is the class label (to be predicted), the User-ID identifies the author, and the Tweet-text the raw tweet

    count: For these files, we have pre-processed the corresponding tweets, and have recorded the term frequency for a subset of words (filtered by tfidf)
                    
    tfidf: For these files, we have pre-processed the corresponding tweets, and have recorded the tfidf (term frequency inverse document frequency) value a subset of words (pre-filtered by tfidf). 
    
    glove300: For these files, we have pre-processed the corresponding tweets, and have mapped each word to its pre-trained word embedding (GloVe) and averaged the embeddings of all words in the tweet
    
        Remark 1: The glove300 feature representation is by far the largest, and depending on your hardware and code may lead to slowest model development. You may want to choose a different data representation and/or downsample the training data.
    
        Remark 2: Some glove300 feature vectors are all 0. This is because none of the words in the Tweet was in the vocabulary on which GloVe embeddings were trained originally.

Finally, 'vocab.txt' contains the vocabulary after tfidf-filtering (underlying the count and tfidf files), mapping each word to a unique identifier (ID), of the form 
    word \tab ID (newline)

