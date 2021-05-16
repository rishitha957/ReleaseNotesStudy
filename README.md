# Analysing Release Notes of Python Libraries
![risha](https://user-images.githubusercontent.com/42757231/99178239-0a095380-2737-11eb-8f94-75ca8f069377.png)
![iittp](https://user-images.githubusercontent.com/42757231/99178231-f3fb9300-2736-11eb-8942-0cde97e79d3b.png)

# What's inside ReleaseNotesStudy Repository?
1. We have a [releaseNotesDS.ipynb](https://github.com/rishitha957/ReleaseNotesStudy/blob/master/releaseNotesDS.ipynb), which helps in extracting GitHub urls of Python Libraries or Frameworks sorted based on maximum number of stars and releases and stores it in a csv file. 
2. We also have a dataset [python_libraries - python_libraries.csv](https://github.com/rishitha957/ReleaseNotesStudy/blob/master/python_libraries%20-%20python_libraries.csv), which have columns [github link, Link to Release Notes present in Website, Link to GitHub Release Notes, XPath to the link of indivual version's Release Note]
3. We then have [AnalyseReleaseNotes.ipynb](https://github.com/rishitha957/ReleaseNotesStudy/blob/master/AnalyseReleaseNotes.ipynb), which takes [python_libraries - python_libraries.csv](https://github.com/rishitha957/ReleaseNotesStudy/blob/master/python_libraries%20-%20python_libraries.csv) as input, and extracts the text from the Release Notes, after preprocessing, embedding, and computing similarity, initial list of relevant sentences to the query is stored in [deprecated_information2.csv](https://github.com/rishitha957/ReleaseNotesStudy/blob/master/deprecation_information2.csv)
4. This is now again taken as input by [postprocessing_results.ipynb](https://github.com/rishitha957/ReleaseNotesStudy/blob/master/postprocessing_results.ipynb) to again seperate Deprecation and Replacement related information, and stored in files [deprecated_information_post_processed_1.csv](https://github.com/rishitha957/ReleaseNotesStudy/blob/master/deprecation_information_post_processed_1.csv) and [replacement_information_post_processed_1.csv](https://github.com/rishitha957/ReleaseNotesStudy/blob/master/replacement_information_post_processed_1.csv) respectively

# Steps to run ReleaseNotesStudy
After downloading the source code of this repository, you can create your own dataset by running [releaseNotesDS.ipynb](https://github.com/rishitha957/ReleaseNotesStudy/blob/master/releaseNotesDS.ipynb) file. However you should manually extract relase notes of each library from their official website, which is a time consuming task, so it is recommended to test the approach of analysing release notes on the existing [python_libraries - python_libraries.csv](https://github.com/rishitha957/ReleaseNotesStudy/blob/master/python_libraries%20-%20python_libraries.csv) file.

Now using the dataset, you can use [AnalyseReleaseNotes.ipynb](https://github.com/rishitha957/ReleaseNotesStudy/blob/master/AnalyseReleaseNotes.ipynb) script to collect intial set of relevant data, it will stored in the file named deprecated_information.csv. 

The generated csv file will be taken as an input to [postprocessing_results.ipynb](https://github.com/rishitha957/ReleaseNotesStudy/blob/master/postprocessing_results.ipynb) script, to further seperate Deprecation and Replacement related information, they will be stored in files deprecated_information_post_processed.csv and replacement_information_post_processed.csv respectively. These are files are further used to obtain insights about quality of Release Notes.

# Dependencies 
```python
pip install -U selenium
pip install -U pip setuptools wheel
pip install -U spacy
python -m spacy download en_core_web_sm
pip install nltk
pip install tensorflow-hub
pip install -U word_forms
```
Run the above commands in the terminal to install all the dependencies 
# How to contribute to API*Scanner*
Incase of a bug or an enhancement idea or a feature improvement idea, please open an issue or a pull request. Incase of any queries or if you would like to give any suggestions, please feel free to contact Aparna Vadlamani (cs17b005@iittp.ac.in) or Rishitha Kalicheti (cs17b014@iittp.ac.in) or Sridhar Chimalakonda (ch@iittp.ac.in) of RISHA Lab, IIT Tirupati, India.