Name : Andrew Thenedi

Student ID : 18079969D

1.  Data Preprocessing:

    a.  Import all the necessary libraries.

    b.  Load the datafile ‘abcnews-date-text.csv’, which was downloaded
        > from the Kaggle. Due to the computational issue, downsizing
        > the dataset into the first 50,000 records is a
        > suitable solution.

    c.  Remove the stop words for all the records, which I reference the
        > stop words list from
        > [*https://gist.github.com/sebleier/554280*](https://gist.github.com/sebleier/554280)
        > and
        > [*https://stackoverflow.com/a/47091490/4084039*](https://stackoverflow.com/a/47091490/4084039).

    d.  Create a new feature for the cleaned headline text, name
        > as ‘cleaned\_headline\_text’. The first updated 5 records are
        > as follow:

> ![](media/image8.png){width="5.630208880139983in"
> height="1.515825678040245in"}

1.  First Visualization:

    a.  Plot the top 20 words that appear the most from the records. We
        > observe that the word ‘police’ appears the most frequent for
        > such a dataset:

> ![](media/image9.png){width="6.213542213473316in"
> height="3.3567410323709534in"}

a.  Calculate the total number of words and the mean number of words per
    > headline:

> ![](media/image3.png){width="3.8645833333333335in"
> height="0.6041666666666666in"}

a.  Plot the frequency of the headline word lengths distribution by
    > using a standard deviation. We observe that 5 words have the most
    > frequencies among all the headlines:

> ![](media/image10.png){width="6.017899168853893in"
> height="2.8091360454943133in"}

1.  Topic Modelling Using Gensim Library:

    a.  Create a term dictionary of the corpus, in which every unique
        > term is being assigned to an index.

    b.  Covert a list of headlines (corpus) into a headline term matrix
        > using the prepared dictionary.

    c.  For the coherence value of all the algorithms that will be
        > mentioned, we use u\_mass as the indicator for the algorithm
        > performance in this dataset. The reason being is that u\_mass
        > generally compute in a shorter time than using the
        > c\_v indicator. Hence, due to the computational limitation,
        > u\_mass would still give us an accurate result.

2.  LDA (Latent Dirichlet Allocation) Algorithm:

    a.  Build the LDA model by initializing the parameters such as
        > corpus, id2word, and num\_topics. For the initialization
        > stage, we set the num\_topics to 10.

    b.  Compute the coherence score for the LDA model using ‘u\_mass’:

> ![](media/image11.png){width="4.666666666666667in" height="0.53125in"}

a.  For a more accurate parameter value for num\_topics with respect to
    > its coherence value, plot the coherence value for the num\_topics
    > of 10 up to 20. The larger a coherence value, the better
    > performance for the corresponding number of topics. For this
    > algorithm, we observe that 10 topics perform the best, as the
    > coherence value is the highest:

> ![](media/image1.png){width="4.869792213473316in"
> height="2.9967946194225723in"}

1.  Latent Semantic Indexing (LSI) Algorithm:

    a.  Build the LSI model by initializing the parameters such as
        > corpus, id2word, and num\_topics. For the initialization
        > stage, we set the num\_topics to 10.

    b.  Compute the coherence score for the LSI model using ‘u\_mass’:

> ![](media/image4.png){width="4.5in" height="0.3854166666666667in"}

a.  For a more accurate parameter value for num\_topics with respect to
    > its coherence value, plot the coherence value for the num\_topics
    > of 10 up to 20. The larger a coherence value, the better
    > performance for the corresponding number of topics. For this
    > algorithm, we observe that 10 topics perform the best, as the
    > coherence value is the highest:

> ![](media/image14.png){width="5.411458880139983in"
> height="3.3648173665791776in"}

1.  Non-Negative Matrix Factorization (NMF) Algorithm:

    a.  Build the NMF model by initializing the parameters such as
        > corpus, id2word, and num\_topics. For the initialization
        > stage, we set the num\_topics to 10.

    b.  Compute the coherence score for the NMF model using ‘u\_mass’:

> ![](media/image13.png){width="4.541666666666667in" height="0.4375in"}

a.  For a more accurate parameter value for num\_topics with respect to
    > its coherence value, plot the coherence value for the num\_topics
    > of 10 up to 20. The larger a coherence value, the better
    > performance for the corresponding number of topics. For this
    > algorithm, we observe that 11 topics perform the best, as the
    > coherence value is the highest:

> ![](media/image5.png){width="5.32035542432196in"
> height="3.351061898512686in"}

a.  Compute the coherence score for the NMF model using ‘u\_mass’ with
    > 11 topics:

> ![](media/image6.png){width="4.5625in" height="0.4166666666666667in"}

1.  Hierarchical Dirichlet Process (HDP) Algorithm:

    a.  For this algorithm, it does not depend on the number of topics.
        > Thus, we can directly compute the coherence score for the HDP
        > model using ‘u\_mass’:

> ![](media/image7.png){width="4.666666666666667in"
> height="0.6041666666666666in"}

1.  Evaluating All Four Models Performance:

    a.  Extract the maximum coherence value from LDA, LSI, and NMF
        > algorithm’s corresponding lists. Convert all the coherence
        > values of all four algorithms into an absolute value (from
        > negative to a positive value) for plotting purposes. From the
        > resulting plot, we observe that LSI performs the best for this
        > dataset, corresponds to the largest coherence value. Hence, we
        > conclude that LSI is the optimal algorithm:

> ![](media/image12.png){width="4.395833333333333in"
> height="2.8958333333333335in"}

1.  Visualize the LSI Model:

    a.  To conclude our observation, we plot the top words from each
        > topic, resulted from the LSI model. We observe that the word
        > ‘police’ and ‘council’ appear the most from the given dataset
        > of headlines:

> ![](media/image2.png){width="4.864583333333333in"
> height="7.302083333333333in"}
