# Coursera-wk4-assmnt1-scrape
Scraping html with Beautifulsoup
The program will use urllib to read the HTML from the data files below, 
and parse the data, extracting numbers and compute the sum of the numbers in the file.

Python3 code as below:

import urllib.request as ur
from bs4 import *

url = input('Enter the url to scrape - ')

html = ur.urlopen(url).read()
soup = BeautifulSoup(html, 'html.parser')

count_of_spans = 0
sum = 0

spans = soup('span')
for span in spans:
    sum += int(span.contents[0])
    count_of_spans += 1

print('Count ', count_of_spans)
print('Sum ', sum)
