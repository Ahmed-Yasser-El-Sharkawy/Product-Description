# 🛍️ Product Description Generator using Generative AI

This project automates the generation of high-quality, tailored product descriptions using a multi-stage AI pipeline. By leveraging category-specific classifiers and large language models (LLMs), it ensures the generated descriptions are both accurate and engaging across multiple domains such as **soda, clothing, and mobile phones**.

---

## 📌 Features

* ✅ **Automated Product Categorization**: Classifies input products into top-level categories (e.g., soda, clothing, phones).
* ✅ **Specialized Classification Models**: Fine-grained classification using dedicated models for each product type.
* ✅ **High-Quality Descriptions**: Uses LLMs with advanced prompt engineering to generate natural, category-specific descriptions.
* ✅ **Database Integration**: Outputs are stored in a structured, categorized database for downstream use.
* ✅ **Scalable & Modular**: Easily extendable to new product categories.

---

## 🧠 Tech Stack & Skills Used

| Category               | Tools / Libraries                          |
| ---------------------- | ------------------------------------------ |
| **Data Collection**    | Web Scraping (BeautifulSoup, Selenium)     |
| **Data Analysis**      | Pandas, Matplotlib, Seaborn                |
| **Computer Vision**    | CNNs, ResNet-18, VGG-16 (via PyTorch)      |
| **NLP & LLMs**         | spaCy, Transformers, OpenAI API            |
| **Prompt Engineering** | Custom prompt templates per product domain |
| **Storage**            | SQLite / PostgreSQL / MongoDB              |

---

## 🗂️ Project Structure

```
product-description-generator/
├── Data/
│   ├── data_for_product_description.txt           # Raw product titles and details
│   ├── link of data images in drive.txt           # Image links used for classification
│── Saving model stutes/                       # Directory for all trained model files
│ ├── Main_Classifier_best_model.pth         # General classifier model
│ ├── Phone_best_model.pth                   # Specialized model for phones
│ ├── Soda_drinks_best_model.pth             # Specialized model for soda
│ └── best_model (6).pth                     # Possibly older or backup model
│
├── Clothes_Classifier.ipynb                       # Training notebook for clothing classifier
├── Clothing_Model_Classifier.ipynb                # Clothing model logic and training
├── Create_Product_Describetion_Using_LLM.ipynb    # Final LLM-based description generator
│
├── Deploy.ipynb                                   # Initial deployment pipeline
├── Deploy_v5.ipynb                                # Updated deployment pipeline (v5)
│
├── Main-classifier.ipynb                          # Notebook to train main classifier
├── Main_Classifier_Model.ipynb                    # Supporting logic for main model
│
├── Phone_Model_Classifier.ipynb                   # Phone category classifier notebook
├── Soda_Drinks_Model.ipynb                        # Soda category classifier notebook
│
├── README.md                                      # Project documentation (this file)
```



## 🔁 Workflow

1. **Scraping & Preprocessing**: Product titles/images scraped and cleaned.
2. **Step 1: General Classification**
   Predicts main category using CNNs (if image) or NLP models (if text).
3. **Step 2: Specialized Classification**
   Routes input to a category-specific model for fine classification.
4. **Step 3: Prompt-Based Description Generation**
   Constructs structured prompts and generates descriptions via LLM.
5. **Step 4: Storage**
   Descriptions are saved in a categorized product database.

---

## 🛠️ Setup Instructions

1. **Clone the Repo**

   ```bash
   git clone https://github.com/yourusername/product-description-generator.git
   cd product-description-generator
   ```

2. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```

3. **Run Classifier Pipeline**

   ```bash
   python scripts/classify_product.py --input data/sample.json
   ```

4. **Generate Descriptions**

   ```bash
   python scripts/generate_description.py --classified_output data/classified.json
   ```

5. **(Optional)**: Launch EDA notebooks or connect database to view results.

---

## 🧪 Models

* **ResNet-18** & **VGG-16** for product image classification.
* **NLP Classifiers** for text-based product name classification.
* **LLMs** (OpenAI GPT, or local LLMs via Hugging Face) for text generation.

---

## 🔍 Example

```json
Input:
{
  "name": "Coca Cola Zero 330ml",
  "image": "coke-zero.jpg"
}

Output:
"A refreshing sugar-free soda with the same great Coca Cola taste. Perfect for calorie-conscious consumers seeking full flavor in every sip."
```

---

## 📦 Future Enhancements

* Add support for **multilingual descriptions**.
* Integrate **real-time deployment** using FastAPI or Flask.
* Extend to **more categories** like cosmetics, books, and electronics.
* Improve fine-tuning pipeline with **custom LLM training** on product data.

---

## 🤝 Contributing

Contributions are welcome! Please fork the repository and submit a pull request for any enhancements or bug fixes.

---

## 📄 License

This project is licensed under the MIT License.

---

Let me know if you’d like a version tailored for deployment on HuggingFace Spaces or Streamlit!
