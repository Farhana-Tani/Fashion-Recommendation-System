# 👗 Fashion Recommendation System

A deep learning–based **image similarity and fashion recommendation system** that recommends visually similar fashion products from an uploaded image. The system uses **ResNet50 transfer learning** to extract high-level visual features and **K-Nearest Neighbors (KNN)** to retrieve the most similar fashion items.


## 📌 Overview

Finding similar fashion products manually can be time-consuming. This project addresses the problem using **computer vision and deep learning**.

Users can upload an image of a fashion item, and the system:

1. Accepts the uploaded fashion image.
2. Preprocesses the image to `224 × 224` pixels.
3. Extracts deep visual features using a pretrained **ResNet50** model.
4. Applies **Global Max Pooling** to generate a compact feature representation.
5. Normalizes the extracted feature vector.
6. Searches the precomputed fashion-image embeddings using **K-Nearest Neighbors**.
7. Returns the **top 5 visually similar fashion products**.

---

## ✨ Key Features

- 👗 **Image-Based Fashion Recommendation**
- 🧠 **ResNet50 Transfer Learning**
- 🔍 **Visual Feature Extraction**
- 📊 **Image Embedding Generation**
- 📐 **Euclidean Distance Similarity Search**
- 🤖 **K-Nearest Neighbors (KNN)**
- 🖼️ **Image Upload Interface**
- ⚡ **Streamlit Web Application**
- 💾 **Precomputed Image Embeddings**
- 🌐 **Web Deployment**

---

## 🧠 Methodology

### 1. Feature Extraction

The system uses **ResNet50 pretrained on ImageNet** as a feature extractor. The original classification layer is removed and replaced with `GlobalMaxPooling2D`.

```text
Input Image
     ↓
Resize to 224 × 224
     ↓
ResNet50 (ImageNet)
     ↓
Global Max Pooling
     ↓
Feature Vector
     ↓
L2 Normalization
     ↓
Image Embedding
```

The feature extraction pipeline converts each fashion image into a numerical representation that captures its visual characteristics.

---

### 2. Building the Image Embedding Database

The fashion dataset is processed using the ResNet50 feature extractor.

For each image:

```text
Fashion Image
     ↓
ResNet50
     ↓
GlobalMaxPooling2D
     ↓
Feature Vector
     ↓
Normalization
     ↓
Stored as Embedding
```

The generated embeddings and corresponding image filenames are stored using Python pickle files:

- `embeddings.pkl`
- `filenames.pkl`

The repository currently stores the large embedding file using **Git LFS**. citeturn1view2

---

### 3. Similarity Search

When a user uploads an image, its embedding is compared against the precomputed fashion-image embeddings.

The project uses:

**K-Nearest Neighbors (KNN)**

with:

- `n_neighbors = 6`
- `algorithm = brute`
- `metric = Euclidean distance`

The nearest results are then displayed as fashion recommendations. citeturn2view0

```text
Uploaded Image
      ↓
Feature Extraction
      ↓
Image Embedding
      ↓
KNN Similarity Search
      ↓
Nearest Fashion Items
      ↓
Top 5 Recommendations
```

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| **Python** | Core programming language |
| **TensorFlow / Keras** | Deep learning and feature extraction |
| **ResNet50** | Pretrained CNN backbone |
| **NumPy** | Numerical computation |
| **Scikit-learn** | KNN similarity search |
| **Pillow (PIL)** | Image processing |
| **Streamlit** | Interactive web interface |
| **Pickle** | Storing image embeddings and filenames |
| **Git LFS** | Large embedding-file storage |

---

## 📂 Project Structure

```text
Fashion-Recommender-System/
│
├── images/
│   └── archive/
│       └── images/
│           └── ... fashion images
│
├── sample/
│   └── ... sample images
│
├── uploads/
│   └── ... uploaded images
│
├── app.py
├── main.py
├── test.py
│
├── embeddings.pkl
├── filenames.pkl
│
├── requirements.txt
├── runtime.txt
├── .gitignore
├── .gitattributes
├── LICENSE
└── README.md
```

The repository contains the Streamlit application, feature-generation script, pretrained-model pipeline, stored embeddings, and supporting files. citeturn1view0

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/Farhana-Tani/Fashion-Recommender-System.git
```

### 2. Navigate to the project directory

```bash
cd Fashion-Recommender-System
```

### 3. Create a virtual environment

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

For Linux/macOS:

```bash
source venv/bin/activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Run the Application

Start the Streamlit application with:

```bash
streamlit run main.py
```

Then open the local URL provided by Streamlit in your browser.

---

## 🖼️ How to Use

### Step 1 — Upload an Image

Upload a fashion/product image through the Streamlit interface.

### Step 2 — Feature Extraction

The uploaded image is resized and passed through the pretrained ResNet50 model.

### Step 3 — Generate Embedding

The model generates a normalized deep feature representation of the uploaded image.

### Step 4 — Similarity Search

KNN compares the query embedding against the stored fashion embeddings using Euclidean distance.

### Step 5 — View Recommendations

The application displays the **five most visually similar fashion items**.

---



## 🎯 Project Highlights

This project demonstrates practical experience with:

- **Computer Vision**
- **Deep Learning**
- **Transfer Learning**
- **CNN Feature Extraction**
- **Image Embeddings**
- **Content-Based Recommendation**
- **Similarity Search**
- **K-Nearest Neighbors**
- **Streamlit Application Development**
- **Model Deployment**
- **Large File Management with Git LFS**

---


## 📄 License

This project is licensed under the **MIT License**.

---

## 👩‍💻 Author

**Farhana Yeasmin**

🔗 GitHub: [Farhana-Tani](https://github.com/Farhana-Tani)

---

⭐ If you find this project useful, consider giving the repository a star!
