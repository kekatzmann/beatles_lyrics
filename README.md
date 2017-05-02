# Analyzing Beatles lyrics with NLP

This repository contains work that utilizes natural language processing techniques, including topic modelling, sentiment analysis, and word2vec word relationships, to gain insight into the Beatles' songwriting.


### Scraping azlyrics.com
The [scrape_azlyrics.ipynb](https://github.com/kekatzmann/beatles_lyrics/blob/master/notebooks/scrape_azlyrics.ipynb) notebook contains work that scrapes [azlyrics.com](http://www.azlyrics.com/) to acquire the lyrics, song titles, and album titles of a band. Only the url of a band page is required. However, please be a good citizen of the internet, and do not spam their site with requests. If you need to acquire a lot of lyrics quickly, there are many sites available from which you can download lyrics for a small fee.


### Natural Language Processing
The [lyric_modelling_exploration.ipynb](https://github.com/kekatzmann/beatles_lyrics/blob/master/notebooks/lyric_modelling_exploration.ipynb) notebook contains natural language processing techniques performed on Beatles lyrics to gain insight into their songwriting. The techniques include topic modelling to understand what the Beatles wrote about, sentiment analysis to understand the feeling of their lyrics, and word2vec to understand the relationships among their words.

<b>Topic Modelling</b><br>
Topic modelling was performed using two machine learning techniques: latent Dirichlet allocation (LDA), and non-negative matrix factorization (NMF). LDA seemed to consistently find "yellow" and "submarine" in one topic (which kind of makes sense, as their song "Yellow Submarine" frequently repeats those words), but I found it very difficult to make any sense out of the other topics. NMF, on the other hand, yielded much more comprehensible topics. The final model was designed to find three topics. The first topic appeared to be about romantic, enduring love (it included: "love", "need", and "always"), the second topic appeared to be about the loss of love (it included: "want", "girl", "never", and "back"), and the third topic appeared to be about a more youthful, playful love (it included: "yeah", "baby", "feeling", and "honey"). The Beatles' reputation of singing about girls and love appears to hold up here pretty well.

<b>Sentiment Analysis</b><br>
Sentiment analysis was performed the lyrics by each line using TextBlob. This produced a couple of interesting findings. For one, there appears to be a decrease in the sentiment of their lyrics over time, and a significant decrease in sentiment towards the end of their tenure. In fact, their first album was their most positive album, and their last album was their least positive. One exception to this trend was their album "Help!", which was written as a soundtrack to a movie, so it would likely not reflect their sentiment as accurately. Another finding was that the more positive songs were predominately written by Paul McCartney, and the more negative ones written by John Lennon. Of course these findings are not anything extraordinarily novel; almost any tried-and-true Beatles fan could tell you these things. But it is very cool to see our understanding of Beatles lyrics supported by NLP.

<b>word2vec</b><br>
word2vec analysis was performed using Gensim, PCA, and TSNE to better understand relationships among the words and songs in Beatles lyrics. creating 100-dimensional vectors out of each word yielded some pretty cool results. For one, subtracting the vector "sgt" from the vector "yellow" and then adding "submarine" yielded the vector "pepper". There are a lot of other cool vector manipulations that you can find and perform in the lyric_modelling_exploration.ipynb notebook. Plots were created using PCA and TSNE dimension reduction techniques. 2 dimenional plots can be viewed in the notebook. And here is a 3 dimensional plot of the vectors. I find it incredible how these arms formed.

<div>
    <a href="https://plot.ly/~kekatzmann/1/?share_key=6T9Ho51vrZCjBnsM76VRtF" target="_blank" title="Plot 1" style="display: block; text-align: center;"><img src="https://plot.ly/~kekatzmann/1.png?share_key=6T9Ho51vrZCjBnsM76VRtF" alt="Plot 1" style="max-width: 100%;width: 1114px;"  width="1114" onerror="this.onerror=null;this.src='https://plot.ly/404.png';" /></a>
</div>
