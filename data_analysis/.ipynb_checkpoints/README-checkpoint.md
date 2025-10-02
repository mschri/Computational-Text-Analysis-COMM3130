## Data analysis notebooks for COMM3130 Group Data Project

* This folder should contain the a series of Jupyter notebooks you create to do the data analysis.

* Update this `README.md` file to document the notebooks and give a short description of what each one does.

Description:

* There will be a total of 5 notebooks for an analysis of each decade of articles for Part 1 Analysis
  * There are a total of 1000 articles across decades (200 articles per decade corpus)

* Each notebook will utilize the following functions/means of analysis:
   * We inserted the "functions" notebook into this folder to apply the following functions:
  [For Frequency Analysis/Creating Word/Phrase Lists]
    * tokenize()
    * get_ngram_tokens()
    * Counter()
  [For Context analysis]
    * make_kwic()
    * sort_kwic()
    * print_kwic()
  [Sentiment Analysis]
    * VADER algorithm & related functions (looked at polarity scores)
  [For comparing across decades]-in a separate notebook
    * Keyness analysis-based on token & bigram lists; used .get() function & other basic arithmetic
      operations (base size=10,000 words)


The overall concept/hypothesis of analysis:
* Hypothesis: following the J&J recall, and therefore a more established golden-standard and protocol by which companies could and should follow, the effectiveness of communication strategies over time should increase

The outline of analysis steps:
[Part 1 Analysis: Individual decade corpus (basic text analysis)]
* 1) Dimension one: Popular words/phrases (Frequency Lists)
  * Obtain single word (token), bigram, & tri gram lists (using/applied Counter(), .most_common(), & any other related functions) per EACH decade corpus
* 2) Dimension two: Context-using KWIC functions
   * Step 1: "J&J Word List": We developed a list of significant words (this analysis located within the first 1980s analysis notebook) from a text analysis of a case study looking at crisis communication strategies centered on the J&J famous Tylenol Response (link to the case study: https://www.ou.edu/deptcomm/dodjcc/groups/02C2/Johnson%20&%20Johnson.htm)
      * Developed list using basic text analysis steps: loaded the text file, tokenized and normalized the text, eliminated stop words, then applied a counter function to find most commonly used words
    * Step 2: Then used this list in each decade corpus to compare the usage of some of these words within each decade's respective corpus by comparing how each words appear in each corpus with KWIC functions
* 3) Dimension Three: Sentiment analysis: Using VADER technique
  * Used VADER algorithm to obtain a polarity score per decade corpus

[Part 2: Comparison across decades]
    * create a separate notebook consisting of mostly written comparisons/observations of how each dimension of analysis per decade corpus compares to each other
* 1) (Dim 1) Word Frequencies:
     * Using Keyness analysis (normalized frequencies) followed by written observations of results
* 2) (Dim 2) Context dimension: comprised of written observations, examining features of words within the J&J word list & how they appear in each decade corpus
     * i.e. which words appear at all (using Counter function)
     * Compare the ones that do appear how they are used (Words that appeared most often: safety,
       example, consumer)
* 3) (Dim 3) Sentiment analysis: written observations/interpretations of the VADER scores
     * Determine if any potential common techniques gathered from these observations?


Most of analysis (particularly part 1) followed text analysis steps:
* Load in relevant functions for analysis & each respective decade text file
* Eliminate table of contents
* Create list of the documents
* Create list of tokenized docs (in doc list)
  * Created list of counter objects per doc (so a total list of counter objects)-tried within in the first (1980s) analysis notebook-found that wasn’t particularly meaningful/helpful, so decided to flatten total list:
* Flattened the list of tokenized docs (to create a whole list of words across all 200 docs)
  * Eliminate stop words within each text for following:
      * Applied counter function to filtered total list
      * Then found: top 50 words (using the filtered list)
      * Repeated steps for created bi and trigram lists
* Compare use of words in decade corpus against the J&J word list, via KWIC functions (against the unfiltered, flattened list)
  * determine how much each of these words used within the respective corpus were positive, negative, etc.
* Applied VADER functions to the normalized decade text (the unfiltered text-as in, included stop words, and just normalized)