Webscrape_github
This is a cleaned up version of my webscrape code that begins with a set or urls of startup companies typically 
downloaded from Crunchbase with a given search pattern. The current input file (included in this repo) 
is Printingtot_v4.csv.

The code then scrapes the text from the front page (the Scrapy package is used):

sitep=response.xpath('//p/text()').getall()

The spider MySpider first modifies the input url list (which is accompanied by other data from Crunchbase including

'Organization Name','Headquarters Location','Full Description','Website')

and removes non-US companies and cleans up for nan records.

The parse function takes the response and pulls off the text and the urls and also replaces unreadable characters 
(possibly this would not be necessary with proper specification of file code as utf-8).

The principal output is a file that includes, for each record, the scraped url, the company name and the text. 
The current name is Ptotal_v2.cor.

Currently, searches (such as "inkjet") when successful go to basic pipeline and get stuff printed out in a separate file.