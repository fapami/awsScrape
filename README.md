# cloudScrape

AWSScrape is a tool designed to scrape SSL certificates from all AWS IP ranges, searching for specific keywords in the certificates' Common Name (CN), Organization (O), and Organizational Unit (OU) fields.

cloudScrape: I have made my own version of the tool that can also scrape Google Cloud ranges and I may add other providers in the future. This project is for my own purposes only, if you would like to please support the original creator of awsScrape: [https://github.com/jhaddix/awsScrape](https://github.com/jhaddix/awsScrape)

[![Twitter](https://img.shields.io/badge/twitter-@jhaddix-blue.svg)](https://twitter.com/jhaddix)

## Installation

1. Clone this repository:

```
git clone https://github.com/fapami/cloudScrape
cd cloudScrape
```

## Usage

Run the script as follows:

```
go run cloudscrape.go -keyword=<KEYWORD>  
```

With all of the cloud providers:

```
go run cloudscrape.go -cloud-provider aws,gcloud -keyword <KEYWORD>
```

| Argument   | Description                                                                                                  |
|------------|--------------------------------------------------------------------------------------------------------------|
| -c -cloud-provider   | Cloud Provider(s) to scan (aws, gcloud) |
| -region   | Region(s) |
| -exclude-region   | Exclude region(s) |
| -keyword    | Provide a single keyword to search for in SSL certificates |
| -output | Provide an output file to store results within |
| -randomize | When set, randomize the order in which IP addresses are checked |
| -threads | Specify the number of concurrent threads (default 4) |
| -timeout | Specify the number of seconds to timeout an SSL connection (default 1) |
| -v -verbose | Enable verbose mode |
| -w -wordlist | Specify a file of keywords to check for (on newlines) |

The script will parse the SSL certificates from the AWS or Google Cloud IP ranges and display any matching your KEYWORD with the IP addresses of the matching certificates.

Please note that iterating through all AWS & Google Cloud IP addresses and checking SSL certificates WILL take a long time to complete.

=================================================================================================================================================

Disclaimer: Usage without a customers permission may constitute a violation of AWS AUP or Google Cloud Security Policy:

* https://aws.amazon.com/security/penetration-testing/
* https://aws.amazon.com/aup/
* https://support.google.com/cloud/answer/6262505?hl=en

Use Responsibly
