# Lab: Insecure direct object references

Click on Live Chat and message Hal.

Turn on proxy and click on View Transcript. Notice that the requests reference a chat transcript by value `2.txt`, which is likely an incrementing number. Change the requests to `1.txt` and inspect the downloaded file to see that it has carlos' password in it. Login as carlos to complete the lab.