# Resume Analysis and Skill Comparison
This project provides an automated way to extract, preprocess, and analyze resumes against a predefined set of desired skills. It uses Natural Language Processing (NLP) and machine learning techniques to evaluate resumes, identify key skills, and visualize the results through charts and word clouds.

## Features
- `Resume Extraction`: Extracts text from .docx files in a specified folder.
- `Text Preprocessing`: Cleans and preprocesses the extracted resume text using Spacy, removing stop words and non-alphanumeric characters.
- `Skill Matching`: Compares resumes against a set of desired skills to calculate a skill match score.
- `Entity Extraction`: Uses Named Entity Recognition (NER) to extract entities like skills, education, and experience.
- `Visualization`: Provides several visualizations including:
 - Bar charts showing skill match scores across resumes.
- Word clouds to visualize the most prominent skills in the resumes.
- Comparison of the top resumes based on specific skills.

## Requirements
```
Python 3.x
Libraries:
matplotlib
spacy
scikit-learn
wordcloud
python-docx
```
### Installation
Clone the repository:
Copy code
```
git clone https://github.com/yourusername/resume-analysis.git
```
### Navigate to the project directory:

Copy code
```
cd resume-analysis
```
### Install the required packages:

Copy code
```
pip install -r requirements.txt
```
### Download and install the SpaCy language model:
Copy code
```
python -m spacy download en_core_web_sm
```
### Usage
`Extracting Resumes`: Place your .docx resumes in the specified folder. The code will automatically extract the text from these files.

### python
```
folder_path = 'path/to/resume/folder'
resumes = read_resumes_from_folder(folder_path)
```
`Preprocessing Text`: Preprocess the extracted text to remove stop words and non-alphanumeric characters.

### python
```
preprocessed_resumes = {name: preprocess_text(text) for name, text in resumes.items()}
```
`Extracting Entities`: Use NER to extract skills, education, and experience from the resumes.

### python
Copy code
```
resume_entities = {name: extract_entities(text) for name, text in preprocessed_resumes.items()}
```
`Skill Matching`: Compare the resumes against a predefined set of skills.

### python
Copy code
```
skill_keywords = ["python", "machine learning", "data analysis", "nlp"]
resume_scores = compare_resumes_based_on_skills(preprocessed_resumes, skill_keywords)
```
`Visualizations`: Visualize the skill match scores using bar charts and word clouds.

### python
Copy code
```
visualize_skill_comparison(resume_scores, top_n=20)
generate_wordcloud(preprocessed_resumes["resume1.docx"], title="Resume 1 Word Cloud")
```
### Visualizations
- `Bar Chart`: Displays the top resumes based on skill match scores.
- `Word Cloud`: Generates word clouds for individual resumes to highlight frequently mentioned skills.
- `Top Resume Comparison`: Compares the skill scores of the top resumes.
### Example
To run the comparison and visualization:

### python
Copy code
```
compare_top_resumes(resume_scores, skill_keywords, top_n=5)
```
This will produce a bar chart comparing the top resumes based on their skill match scores against the provided skill keywords.
