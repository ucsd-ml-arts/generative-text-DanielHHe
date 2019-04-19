# Project 1 Generative Text

Daniel He, dhe@eng.ucsd.edu , dhe@ucsd.edu

## Abstract

- The main idea is write a program to train on drawing instructionals so that the output can be a drawing instructional based on a given input. (In this case the first instruction.)
- The text training method used a character based RNN running on tf.keras and eager execution as shown in the Shakespeare example.
- Using a familiar method allowed for various tweakings of the text generation and training. For the training, I experimented with different numbers of epochs with 10, 20, 30, and 40. 30 worked best in my case because it added a certain level of uncertainty (which can further be tweaked with the temperature in the text generator) and also runs in a reasonable amount of time. (The need for saving time was because my corpus was still being tweaked and constantly retraining taakes a lot of time, especially if the number of epochs is greater.) This choice makes sense because it allows for the user to have a whacky instruction set that needs human interpretation (as shown in the various art drawn with the instructionals), adding the human art element into the mix. 
For text generation, I wanted the output to have a 1 through 10 instruction format. Originally, I had the input be the title of what the user wanted to draw, but this led to very bad outputs (this is why the training set still has the titles "How to draw a -----", in them). To do this the text generation function was given the first few words of the first instruction and ran until hitting an end line character. This output would then be cascade fed in the text generation function again so that the input to the second instruction is the completed first instruction. (The third would have an input of the first and second and so on). In this way 10 instructions can be generated. 
- Experimenting with the temperature showed that lowering the temperature had the best results. Higher temperatures outputted less predictable results and because my training set is small and the number of epochs is small, I wanted more predictability.
- Finally, the results were drawing instructionals that require some human interpretation to follow through. Each of the instructionals will include at least 1 drawing, just to see how these instructions can be interpreted. The titles of each result were chosen based on the interpreted art of various test subjects. 
- There are of course a few issues. Because the corpus is small, some words generated do not actually exist which results in some unfortunate instructions. While, the instructions can sometimes be hilariously bad, other times it is just plain terrible, it is clear that the more samples the better. 

## Files

- corpus.txt - your training data.
- Instruction_G.ipynb - this both trains and generates the text output
- myspider.py - webscraper used

## Results

- results are done with final tweaks as described in the abstract, in addition titles are chosen by the user
- I1.pdf - input text used was "Draw a line", there are several generated instructions in the pdf

## Notes

The webscraper was ran on google colab so that the scrapy tool could be installed. After running '!pip install scrapy', the webscraper code can be written in myspider.py. This code is half commented. The first run should scrape  the first sites and then commenting out the code and renaming the output, run again to scrape the next sites. (These site URLs were obtained using the url-extractor site.) After these 2 output files are obtained, combine them and rename it corpus.txt.

## Reference

Project requirements: [doc](https://docs.google.com/document/d/13ueceIyuUc4ATD7B-SFZK641MycFZ57eZ9n1lQ3Y1CM/edit?usp=sharing)
Extracting URLs: http://convertcsv.com/url-extractor.htm
Scrapy Examples: https://scrapy.org/resources/
