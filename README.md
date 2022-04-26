# Sainsbury's Delivery App Reviews Analysis
This project aimed to employ natural language processing techniques to understand customer sentiments towards Sainsbury's grocery delivery app and extract frequent pain points that customers face to suggest management solutions. This analysis is centred around reviews from the Google Play Store and they are compared to 6 other delivery apps from the following supermarkets: Tesco, Asda, Aldi, Morrison's, M&S, and Waitrose.

![Webp net-resizeimage](https://user-images.githubusercontent.com/67346082/165345717-66f4a829-49f5-43b6-b2a6-bdf75d226bd9.png)

## How It's Made:

**Tech used:** Python, NLTK, TextBlob, Hugging Face - BERT model, Matplotlib, Seaborn, Numpy, Pandas, Wordcloud

This project uses an open-source Google Play Store scraper to retrieve reviews for each company's app. The reviews were then classified into one of three categories depending on the number of stars: 1-2 were negative, 3 were neutral, and 4-5 were positive. To understand the sentiment that each review conveyed and compare it to the category it was classified, three models were tested: VADER, TextBlob, and BERT. The BERT model has the highest accuracy in accurately classifying the reviews to their pertaining category at a 79.12% accuracy, cutting the number of misclassifications by nearly half. 

To extract the most common complaints and compliments that customers had from the data NLTK's sentence tokeniser was used to split the reviews into sentences, which was followed by applying NLTK's tweet tokenizer to split the reviews into words. The words were then normalised by lowercasing them and by combining compound words with multiple spellings, but identical meanings such as checkout, Clubcard, login, logout, sparkcard etc. Lastly, the resulting tokenised words from each review were lemmatized by using part-of-speech tagging to ensure the resulting lemmatized words were classified based on their definition in context. Lastly, before performing any further analysis, punctuations, digits, symbols, and different sets of stop words were removed based on the analysis being performed

## Recommendations to management

Given the results of the analysis, we suggest investigating the functionality issues by reviewing errors which have been recorded by the app during the checkout and payment processes. Addressing these issues must be a priority given most of the negative reviews received have resulted from failures during these stages. Furthermore, to alleviate the frustration felt by customers who are unable to log in after several attempts it is advised to trigger a message to contact support directly or move to the web version to complete the order. This would serve as a short-term solution whilst the issue is investigated and solved. 

Additionally, an area which can prove to be beneficial for the customer experience would be to create an autoresponder that engages with reviews, given the company only responds to a mere 0.2% of reviews. This can be implemented by leveraging hundreds of data points containing interactions of Sainsbury’s Twitter account with customer complaints. This would improve Sainsbury’s brand and may translate to lower customer attrition.

Moreover, after reviewing the app, it was found that it takes users a minimum of 5 clicks to reach a point of contact and an in-app browser i.e. it is a cumbersome process. This can be streamlined by an in-app chatbot or an in-app menu to avoid customers leaving the shopping experience. 

Lastly, it is advised to supplement the reviews dataset by incorporating topic modelling and tagging to better classify reviews, in turn providing better data to train the chatbot and enable enhance customer issue tracking. Furthermore, the sentiment analysis performed with this data can also be expanded to include data from the Apple Store, Twitter, and Facebook to provide a more comprehensive view of customers’ app-based ordering experience. 


## Future Optimizations

Future optimizations that I look forward to making include: 
1) Create a dashboard that updates periodically with the mean sentiment of the reviews left by customers.
2) Perform text generation to create replies to the reviews using data from Sainsbury's Twitter account.
3) Perform a parallel analysis with the Apple Store application and compare the results, perhaps one app performs significantly better. 
4) Enhance the dataset with data from multiple sources.

I think these would be great additions to the analysis and would extend the recommendations and solutions beyond the Android app.

## Lessons Learned:
1) How to implement one of Hugging Face's pre-trained BERT models to obtain sentiment from text. Having never used transformers, it was incredible to use such an accurate model that is fairly quick given its results. Will certainly use the text classification model by Hugging Face in future.

2) I learned that to obtain the best results when lemmatizing text content it is best to combine a part of speech tagger to ensure that the lemmatization of words is done according to the appropriate part of speech. Particularly when using WordNet lemmatizer as this tool will automatically assume the word is a noun, which is incorrect in many cases, and will likely lead to mistaken conclusions.
