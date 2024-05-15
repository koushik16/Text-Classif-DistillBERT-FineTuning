**Fine Tuning DistillBERT for Text-Classification of Youtube Comments**<br />

****

**DataSet Preparation**
- When you're setting out to create your own dataset for text classification, aim for a comprehensive collection. You'll need at least 2000 words overall, and your dataset should include at least three distinct categories. 
- For our text classification, we used three categories: sports, movies, and technology. Each of these categories should have a minimum of 1000 examples, which could be anything from a poem to a paragraph from a book. 
- Additionally, I've utilized the YouTube v3 API to extract video comments, which can provide a rich source of real-time, user-generated content. For our project, we divided the dataset into training and test sets in an 80-20 split. You have several options for gathering data: you might consider web scraping, utilizing non-confidential documents you already have, or even generating text with tools like ChatGPT.


---

In our project, we used the DistilBERT model from the Hugging Face Transformers library, which is a lighter version of BERT optimized for speed and efficiency, making it suitable for environments where computational resources are limited. Our dataset was carefully cleaned to ensure high data quality, which is crucial for effective model training.

*For preprocessing and cleaning the dataset, several steps were crucial:*

1. Tokenization: We converted the raw text into tokens that could be processed by DistilBERT. This involves splitting the text into words or subwords, which are then mapped to indices in a pre-defined dictionary.

2. Cleaning Text: The dataset, especially the comments extracted from YouTube, required thorough cleaning to remove noise and irrelevant content. This included stripping HTML tags, correcting misspellings, removing non-alphanumeric characters, and converting all text to lowercase to maintain consistency.

3. Removing Outliers: YouTube comments often contain spam and off-topic remarks. We implemented filters to identify and remove such outliers, ensuring the data relevancy and quality were maintained.

4. Data Augmentation: To enhance the diversity and volume of our training data, we employed techniques like synonym replacement and back translation, which helped in creating varied linguistic structures without altering the original meanings.

---

*Also in the project, we used a suite of sophisticated libraries and tools tailored to our specific needs:*

1. Transformers (by Hugging Face): This library provided the DistilBERT model, a distilled version of the BERT model which retains most of its original's effectiveness but is much lighter and faster. This was essential for efficiently training our model with limited computational resources.

2. Sklearn (Scikit-learn): We used Sklearn extensively for data preprocessing, splitting the dataset into training and test sets, and for implementing machine learning algorithms that provided baseline comparisons for our neural network model. Its robust functionality for model evaluation, such as generating accuracy scores and confusion matrices, was crucial for our validation processes.

3. Langdetect: This library was particularly useful in the initial stages of data preprocessing, where it helped us detect and filter out non-English comments from the YouTube data. This ensured uniformity in our dataset, which is critical for maintaining model accuracy across data.

3. Google API Client: Essential for interfacing with the YouTube Data API, this library allowed us to programmatically extract comments from specific videos, thus automating the data collection process and ensuring a rich dataset derived from diverse video content.

4. CUDA: NVIDIA’s CUDA technology was utilized to leverage the power of GPUs for our training process, significantly reducing the time required for training iterations and allowing more complex models to be trained faster.

5. Data Cleaning Tools: We employed a range of Python libraries for effective text cleaning, including regular expressions (for removing unwanted characters and tags), Pandas (for data manipulation and cleaning), and NumPy (for numerical operations).

Each library was chosen for its ability to streamline the project workflow, from data collection and cleaning to model training and evaluation. By integrating these tools, we maximized our project’s efficiency and accuracy.

---

The fine-tuning process involved setting up a Trainer in the Hugging Face library, using our split datasets — 80% for training and 20% for testing. After training, our model achieved a test accuracy of approximately 86%. This high level of performance demonstrates the efficacy of DistilBERT for text classification tasks involving varied categories like sports, movies, and technology.

To improve the model's accuracy further, increasing the dataset size and enhancing the pre-processing steps could be beneficial. Given that YouTube comments can include a significant number of outliers, refining our data cleaning process to remove these outliers would likely yield better results. Additionally, expanding our dataset would allow us to experiment with more hyperparameters during the fine-tuning process, potentially enhancing the model's ability to generalize across more diverse data.


