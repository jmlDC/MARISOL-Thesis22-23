Media Frames Corpus 4.0
=======================

This dataset represents version 4.0 of the Media Frames Corpus, released on March 5, 2021. It contains labeled and unlabeled articles on six issues from 14 newspapers covering the years 1990-2014, though some issues have broader coverage.

## File structure

Each of the six sub-directories contains files associated with one of the six issues.

For each issue, there are two .json files. One contains the text for each article, along with basic metadata (newspaper source and date). The other file contains the annotations for a subset of articles, as well as the text of the article as it was annotated (which occasionally involves minor modification from the original text by the annotators).

The text of each article was shortened to 225 words, rounded up to the end of the paragraph. The article ID and the word "PRIMARY" were also prepended to the beginning of the text.

The codes.json file in this directory contains a mapping from numeric codes to tones and frames.

## Annotations

In most cases, annotated articles were annotated by at least two annotators. There are three categories of annotations: relevancy, framing, and tone. For each category, the json file contains the annotations from each annotator. Note that different annotators annotated different categories in some cases, and not all categories have been annotated for all articles. 

Relevancy (irrelevant) is simply a judgment (by each annotator) as to whether or not the article is relevant for the issue (as defined in the paper).

Tone is a judgement as to whether the article is neutral, or is (implicitly or explicitly) pro or anti towards the default position on the issue. (For example, for immigration, "pro" suggests a pro-immigration position. Note that for gun control, these were annotated as pro or anti gun, so "anti" is actually pro gun control).

The framing annotations identify spans of text that cue each of 15 framing dimensions, including special codes for the "primary" frame of the article, as well as for the headline, although these were not always used precisely as intended. In general the word "PRIMARY" at the start of the article is where annotators identify the primary frame. 

For framing, the start and end of each span is given as a 0-based index into the text.

In addition to the detailed annotations, an attempt was made to resolve the consensus of the annotators for the (primary) tone, primary frame, headline frame, and whether or not the article is irrelevant, each of which occurs as an additional field for each article.

## Sampling issues

For most issues, the .json file with unlabeled articles contains all articles on the issue from the sources used, based on an external database, as described in the original paper. The annotated articles are approximately a random sample from the full set of articles (following de-duplications). There are a few exceptions to this however. 

First, the availability of some sources changed over time, thus there is a slight change in composition of sources for some issues.

Second, gun control was later extended, such that articles from 2015-2018 are over-represented among the annotated articles.

Third, the data collection for climate change unfortunately failed, and was not noticed until later, such that the unlabeled articles for that issue does not include the full set of articles that should have been collected. As such, it is less comprehensive than the other issues, and any patterns noticed over time should be treated with skepticism for this one issue.

## A note on sources

14 named newspapers are listed among the sources in this dataset. Most of these are self-explanatory (e.g., "new york times"), but a few require clarification: "daily news" is the New York Daily News. "herald-sun" includes articles from both the Durham Herald Sun and the Chapel Hill Herald, which are affiliated. Also, note that the St. Petersburg Times was renamed to the Tampa Bay Times in 2012. These two sources represent the same paper, but the individual names have been preserved in this dataset.

## Citation

To cite this dataset, please cite the following paper:

```
@inproceedings{card.2015,
  title = {The Media Frames Corpus: Annotations of Frames Across Issues},
  author = {Dallas Card and Amber E. Boydstun and  Justin H. Gross and  Philip Resnik and Noah A. Smith},
  year = {2015},
  booktitle={Proceedings of ACL},
  url={https://www.aclweb.org/anthology/P15-2072/},
} 
```


