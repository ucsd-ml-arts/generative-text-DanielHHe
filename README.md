# Project 1 Generative Text

Your Name, dhe@eng.ucsd.edu , dhe@ucsd.edu

## Abstract

Include your abstract here. This should be one paragraph clearly describing your concept, method, and results. This should tell us what architecture/approach you used.

## Files

Briefly decribe the files that are included with your repository:
- corpus.txt - your training data.
- Instruction_G.ipynb - this both trains and generates the text output
- myspider.py - webscraper used

## Results

- results are done with final tweaks as described in the abstract, in addition titles are chosen by the user
- results1 - input text used was "Draw a line"

## Notes

Any implementation details or notes on repeating your work. 

The webscraper was ran on google colab so that the scrapy tool could be installed. After running '!pip install scrapy', the webscraper code can be written in myspider.py. This code is half commented. The first run should scrape  the first sites and then commenting out the code and renaming the output, run again to scrape the next sites. (These site URLs were obtained using the url-extractor site.) After these 2 output files are obtained, combine them and rename it corpus.txt.

## Reference

Project requirements: [doc](https://docs.google.com/document/d/13ueceIyuUc4ATD7B-SFZK641MycFZ57eZ9n1lQ3Y1CM/edit?usp=sharing)
Extracting URLs: http://convertcsv.com/url-extractor.htm
Scrapy Examples: https://scrapy.org/resources/
