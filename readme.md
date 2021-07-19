
# Introduction
- In this work, we constructed a dataset of about 1.5 million URLs with 51% of them as legitimate and 49% of them as phishing. The legitimate URLs came from the Common Crawl (www.commoncrawl.org) open web searching database, while the phishing URLs came from the popular PhishTank (www.phishtank.com) phishing website repository. In more details, we followed the top Alexa (alexa.com) domain list to select the corresponding URLs from the Common Crawl database until we obtained a total of 800,000 unique URLs; because these URLs were crawled from 5,341 of the top 5,642 Alexa domains (301 domains do not have URLs in the database), it is reasonable to assume that they are all legitimate URLs. Manual inspection of samples of them confirmed our assumption, and other researchers such as Bahnsen et al.
also considered the URLs in the Common Crawl database as legitimate. We obtained from the PhishTank repository 26,711 confirmed phishing URLs that were online on 01/09/2018 and 732,774 confirmed phishing URLs that were offline at that time for a total of 759,485 unique phishing URLs.
- Table 1 exemplifies five legitimate URLs and five phishing URLs in our dataset. We can see that legitimate and phishing URLs are often very similar as expected by attackers. Table 2 provides the statistics of our dataset. The most common TLDs (top-level domains) are .com and .net in our dataset. TLDs can be categorized into gTLDs (generic TLDs) that are maintained by the Internet Assigned Numbers Authority (IANA) for use in the Domain Name Systems of the Internet, and ccTLDs (country code TLDs) that are usually reserved for specific geographic locations.


## Table 1

![image](/imgs/table1.png)


## Table 2

![image](/imgs/table2.png)


# how to use:
``` python
import dill
dill_file="vonDataset20180426.dill"
with open(dill_file, 'rb') as f:
        pickleData=dill.load( f )
        train_x,train_y=pickleData["train_x"],pickleData["train_y"]
        val_x,val_y=pickleData["val_x"],pickleData["val_y"]
        test_x,test_y=pickleData["test_x"],pickleData["test_y"]
        char_to_int=pickleData["char_to_int"]
print("Feature Shapes:\n")
print("Train set: {}".format(train_x.shape), 
      " Validation set: {}".format(val_x.shape),
      " Test set: {}".format(test_x.shape))
```

#Citation:
@inproceedings{10.1145/3381991.3395602,
author = {Feng, Tao and Yue, Chuan},
title = {Visualizing and Interpreting RNN Models in URL-Based Phishing Detection},
year = {2020},
isbn = {9781450375689},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
url = {https://doi.org/10.1145/3381991.3395602},
doi = {10.1145/3381991.3395602},
abstract = {Existing studies have demonstrated that using traditional machine learning techniques,
phishing detection simply based on the features of URLs can be very effective. In
this paper, we explore the deep learning approach and build four RNN (Recurrent Neural
Network) models that only use lexical features of URLs for detecting phishing attacks.
We collect 1.5 million URLs as the dataset and show that our RNN models can achieve
a higher than 99% detection accuracy without the need of any expert knowledge to manually
identify the features. However, it is well known that RNNs and other deep learning
techniques are still largely in black boxes. Understanding the internals of deep learning
models is important and highly desirable to the improvement and proper application
of the models. Therefore, in this work, we further develop several unique visualization
techniques to intensively interpret how RNN models work internally in achieving the
outstanding phishing detection performance. Especially, we identify and answer six
important research questions, showing that our four RNN models (1) are complementary
to each other and can be combined into an ensemble model with even better accuracy,
(2) can well capture the relevant features that were manually extracted and used in
the traditional machine learning approach for phishing detection, and (3) can help
identify useful new features to enhance the accuracy of the traditional machine learning
approach. Our techniques and experience in this work could be helpful for researchers
to effectively apply deep learning techniques in addressing other real-world security
or privacy problems.},
booktitle = {Proceedings of the 25th ACM Symposium on Access Control Models and Technologies},
pages = {13–24},
numpages = {12},
keywords = {visualization, interpretation, phishing detection, deep learning},
location = {Barcelona, Spain},
series = {SACMAT '20}
}

