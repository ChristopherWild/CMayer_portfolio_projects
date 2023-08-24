# CMayer_portfolio_projects

This repository contains jupyter notebook files for my portfolio projects.

The first project was an analysis of property prices in Victoria, BC. 

Ten years of sales data was collected for single-dwelling houses and condominium in Victoria using Selenium to scrape the data from a real estate website.  The data was then consolidated, cleaned up and set in a data frame format using Pandas.

Pandas was used to analyse the data and to engineer features including postal code, house type and year of sale that would provide extra data for more accurate machline learning . Matplotlib and Seaborn were used to visualize the data, as seen in the example graphs.

Multiple machine learning models were tested using the Scikit-Learn library, including linear regression, support vector machines, random forests and histogram-based gradient boosting regressor. The latter was selected as the final model as it had the most accuracte prediction as measured using mean absolute error and root mean squared error. The root mean squared error for this model was $145638.34.

The second project was a topic modelling analysis of research articles from the scientific journal database, Pubmed, using the search term myalgic encephalomyelitis/chronic fatigue syndrome.

Article data was collected using Requests and Beautiful Soup via the Pubmed API. Relevant information was collected, including author names, article title, abstracts and year of publishing. Information was organized into a dataframe using Pandas.  The abstract information was used to engineer keyword and summary features with the OpenAI library and Text-Davinci. 

Non-Negative Matrix Factorization (NMF), Hierarchical Density-Based Spatial Clustering of Applications with Noise (HDBSCAN) and Bidirectional Encoder Representations from Transformers (BERT) models were used to cluster the articles into topic groups. These models were evaluated based on their ability to group the data into sensical topic clusters, analyzed by evaluating the top relevant terms for each topic. Interestingly, two-dimensional KDE plots showed better cluster separation for the HDBSCAN and BERT models, however, the most logical topic clusters based on the top relevant terms were created by the NMF model. These plots are depicted in this window.

For the NMF model, the titles and abstracts were vectorized using term frequency-inverse document frequency (TFIDF) vectorization and then clustered using the scikit-learn NMF model. The data was then scaled dimensionally to two dimensions, using uniform manifold approximation and projection (UMAP), and a kernel density estimate (KDE) plot was created to visualize the clusters.  

For the HDBSCAN analysis, the abstracts and titles were tokenized and embeded using the Sentence-Transformer all-mnet-base-v2 model, the dimension of the data was reduced using the UMAP technique, and then clustered using HDBSCAN. Following, a KDE plot was created with two-dimensional UMAP data.

The BERT topic respresentation model was created using the scikit-learn count vectorizer, UMAP for dimensional reduction performed using, HDBSCAN for clustering and the Sentence-Transformer all-mnet-base-v2 model.  Two-dimensional UMAP data was plotted on a KDE plot for visualization.

Dash-Plotly was used to create a dashboard with two plots, a intertopic distance map and a bar graph illustrating the top-10 most relevant terms for each topic cluster, for all three models.
