
# Introduction
- In this work, we constructed a dataset of about 1.5 million URLs with 51% of them as legitimate and 49% of them as phishing. The legitimate URLs came from the Common Crawl (www.commoncrawl.org) open web searching database, while the phishing URLs came from the popular PhishTank (www.phishtank.com) phishing website repository. In more details, we followed the top Alexa (alexa.com) domain list to select the corresponding URLs from the Common Crawl database until we obtained a total of 800,000 unique URLs; because these URLs were crawled from 5,341 of the top 5,642 Alexa domains (301 domains do not have URLs in the database), it is reasonable to assume that they are all legitimate URLs. Manual inspection of samples of them confirmed our assumption, and other researchers such as Bahnsen et al.
also considered the URLs in the Common Crawl database as legitimate. We obtained from the PhishTank repository 26,711 confirmed phishing URLs that were online on 01/09/2018 and 732,774 confirmed phishing URLs that were offline at that time for a total of 759,485 unique phishing URLs.
- Table 1 exemplifies five legitimate URLs and five phishing URLs in our dataset. We can see that legitimate and phishing URLs are often very similar as expected by attackers. Table 2 provides the statistics of our dataset. The most common TLDs (top-level domains) are .com and .net in our dataset. TLDs can be categorized into gTLDs (generic TLDs) that are maintained by the Internet Assigned Numbers Authority (IANA) for use in the Domain Name Systems of the Internet, and ccTLDs (country code TLDs) that are usually reserved for specific geographic locations.

! [GitHub Logo](/imgs/table1.png)
![image](https://github.com/vonpower/PhishingDataset/blob/master/imgs/table1.png)
![image](/imgs/table1.png)
! [GitHub Logo](/imgs/table2.png)

Format: ![Alt Text](url)

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
print("\t\t\tFeature Shapes:")
print("Train set: \t\t{}".format(train_x.shape), 
      "\nValidation set: \t{}".format(val_x.shape),
      "\nTest set: \t\t{}".format(test_x.shape))
```
