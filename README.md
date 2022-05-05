# Sentiment-Analysis-on-Yelp-Review

Transformer models have vastly advanced the study of natural language understanding. Sentiment analysis is a sub-field of NLP to infer users’ opinions on products or services from reviews, survey responses and social media in a wide range of application domains. In this analysis, I performed multi-level sentiment classification on Yelp 5-star review data using BERT (Bidirectional Encoder Representations from Transformers). BERT has been demonstrated to achive over 90% accuracy in binary sentiment classifications on many benchmark datasets. Performing multi-level sentiment classification is a challenging task that requires the model to discern the intensity and subtleties of tone. 

Another challenge facing here is long text. Although transformer models can handle long-range dependencies through the self-attention mechanism, most of then have a limit on the input sequence length. The sequence length in this dataset ranges from 3 to 2,344 with 4.7% of training examples exceeding 512 tokens which is the maximum input sequence length of BERT. In addtion, sarcasm, mislabeling and rating bias are common challenges in all NLP tasks which have also been observed in this analysis by visualing attention weights. 

To fine-tune the pre-trained BERT, I froze the embedding and the first 11 encoder layers and fine-tuned the last encoder layer and the fully connected output layer. The learning curve of loss and accuracy over epochs was plotted to minitor overfitting. t-SNE was plotted to visualize the change of embeddings over training epochs and encoder layers. 

The test accuracy after fine-tuning is 61%. Higher accuracy was observed in the 1-star and 5-star classes as they are bounded on one side. The majority of misclassifications take place in the three middle rating levels. The decision boundary of the three middle levels can be controversial even from the perspective of humans. Considering data imperfection, human baseline level and multi-classes, Transformer models have fairly good performance in sensing subtleties in tone and emotions.

Please check the code if you are interested in details: https://github.com/lenglengling/Sentiment-Analysis-on-Yelp-Review/blob/main/Sentiment%20Yelp.ipynb.


#### References
@article{zhang2015character,
  title={Character-level convolutional networks for text classification},
  author={Zhang, Xiang and Zhao, Junbo and LeCun, Yann},
  journal={Advances in neural information processing systems},
  volume={28},
  year={2015}
}

@article{devlin2018bert,
  title={Bert: Pre-training of deep bidirectional transformers for language understanding},
  author={Devlin, Jacob and Chang, Ming-Wei and Lee, Kenton and Toutanova, Kristina},
  journal={arXiv preprint arXiv:1810.04805},
  year={2018}
}
