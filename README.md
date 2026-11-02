# AI Resume Screening & Job Matching Assistant

Upload a resume PDF and paste a job description. The app tells you:

- **Match score** (0–100%)
- **Missing skills**
- **Resume category** (e.g. ML / AI Engineer)
- **Suggestions** to improve the resume

Built with Python, Scikit-Learn, Sentence Transformers (BERT) and Streamlit.

## How it works

1. Load 1,200 resumes and explore them (top skills, experience, education).
2. Turn resume text into TF-IDF features and train a classifier to predict the category. Random Forest scored best at about **61% cross-validated accuracy** across 7 categories.
3. Compare a resume and a job description using `all-MiniLM-L6-v2` embeddings and cosine similarity, combined with how many of the job's skills the resume covers.
4. Show everything in a Streamlit web app.

## Run it

1. Open `AI_Resume_Screening_Job_Matching_Assistant.ipynb` in Google Colab.
2. Upload `resume_dataset_1200.csv` to the Colab files panel.
3. Run all cells. The last one prints a temporary link ending in `trycloudflare.com`. Open it to use the app.

## How to use the app

1. Click **Browse files** and upload your resume as a PDF. It must be a text-based PDF, not a scanned image.
2. Paste the job description you want to compare against into the text box.
3. Click **Analyze**.
4. Read the results:
   - **Match Score:** how well your resume fits the job (higher is better).
   - **Predicted Resume Category:** the type of role your resume looks like.
   - **Missing Skills:** skills the job asks for that your resume doesn't mention.
   - **Suggested Improvements:** what to change to improve your match.
5. To try another job, paste a new description and click **Analyze** again.

Tip: the app only recognises skills from its built-in skill list (about 90 common tech and business skills), so a skill it doesn't know won't show up as missing.
