# LAirBnB Recommender
**Problem:**  
  I'm from Los Angeles & people always ask me what they should check out or where they should stay when they visit.  
  * I don't know.  
  * Los Angeles is huge.  
  * Multiple neighborhoods have similar characteristics.  

**Solution:**  

  <img src="https://github.com/janniec/LAirBnB_Recommender/blob/master/images/lairbnb_logo.png" alt="LAirBnB Logo" align="middle" height=250px>      

  Build a content-based recommender using the neighborhood descriptions found in Los Angeles AirBnB listings.  The recommender will take in the index number for a neighborhood description, and return the descriptions of similar neighborhoods.  

For an overview, please click [here](https://github.com/janniec/LAirBnB_Recommender/blob/master/lairbnb_presentation.pdf "Presentation").

## Tools  
  * NLTK  
    * stopwords  
    * WordPunctTokenizer  
    * sent_tokenize  
    * WordNetLemmatizer  
  * SKLearn  
    * TfidfVectorizer  
    * NMF  
    * LatentDiricheletAllocation  
    * DBSCAN  
    * KMeans  
    * silhouette_score  
    * NearestNeighbors  
    * TruncatedSVD  
    * TSNE  
  * Matplotlib  
  * Regular Expressions  

## Data  
Data was acquired from [Inside AirBnB](http://insideairbnb.com/get-the-data.html), specifically the listings.csv.gz file for all Los Angeles listings as of April 2, 2017.

## Model   
1. Pre-processed neighborhood descriptions.   
   * Removed stop words.   
   * Tokenized & lemmatized.  
   * Vectorized text into bi-grams and sorted based on frequency.   
2. Reduced dimensions into interpretable topics.  
  <img src="https://github.com/janniec/LAirBnB_Recommender/blob/master/images/dimensions.png" alt="Dimensions" align="middle" height=250px>  
3. Clustered listings.  
  * Investigated silhouette scores for KMeans clusters and DBScan clusters.  
  <img src="https://github.com/janniec/LAirBnB_Recommender/blob/master/images/clusters.png" alt="Clusters" align="middle" height=250px>     

See [LAirBnB_neighborhood_topics.ipynb](https://github.com/janniec/LAirBnB_Recommender/blob/master/notebooks/LAirBnB_neighborhood_topics.ipynb).


## Visualization    

2-D t-SNE visualizations of KMeans clusters.  
See [LAirBnB_visualizations.ipynb](https://github.com/janniec/LAirBnB_Recommender/blob/master/notebooks/LAirBnB_visualizations.ipynb) & [Visuals](https://github.com/janniec/LAirBnB_Recommender/tree/master/viz).

## Recommender  

The recommender takes in the index number of a neighborhood description ('input') and the number of desired recommendations. It uses NearestNeighbors to find similar neighborhood descriptions ('output'), filters out outputs that are outside of the input's cluster. The recommender will print out the input's and remaining outputs' neighborhood descriptions.  
See [LAirBnB_recommender.ipynb](https://github.com/janniec/LAirBnB_Recommender/blob/master/notebooks/LAirBnB_recommender.ipynb).

## Next Steps  
Next steps will be to incorporate features of the listings, so as to better tailor recommendations based on pricing, rental type, number of guests, etc.  
