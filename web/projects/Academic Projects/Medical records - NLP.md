# Extraction, Recognition, and Search in Medical Records

This code was developed to automate the management of medical records by performing text extraction, named entity recognition, and enabling precise searches within documents.  
![image](https://github.com/ZinebAissaoui/Projet_S2D/assets/150697197/793232e6-b839-4d6f-9142-f6036ff8d7de)

---

## How the Code Works

### 1. Text Extraction

The code processes medical records in PDF format and detects the presence of scanned images. For native PDFs, it uses the **pdfplumber** library from PyPDF2 to extract textual data. For scanned PDFs, Optical Character Recognition (OCR) is performed using the **doctr** library. The medical records are then stored as `.txt` files for further manipulation.

---

### 2. Named Entity Recognition (NER)

- For **blood test reports**, the code uses the Quaero corpus to train a **Conditional Random Fields (CRF) Tagger** to identify relevant named entities.
- For other types of documents, **regular expressions (Regex)** are used to recognize named entities.  
The extracted metadata is structured using a predefined **JSON schema**, and the information is stored in a JSON database.

---

### 3. Search Engine

The code vectorizes the textual data using **transformers**, creating an embedding file. It calculates similarity scores using **cosine similarity** between the search query and the embeddings of the medical records. Finally, the code displays the similar terms and their context within the medical records.

---

## 4. Repository Structure

- **`Dossier Analyse`**: Contains the code using the CRF Tagger to extract named entities and structure them for JSON storage. Other scripts handle the Quaero database and CRF model training.
- **`Dossier Ordonnance`**: Handles prescriptions, extracting named entities and structuring them into JSON files.
- **`Dossier FichePatient`**: Processes patient records and develops regular expressions (Regex) for entity recognition.
- **`Dossier CR`**: Processes radiology and scan reports, extracts named entities, and structures them into JSON files.
- **`Jsons`**: Stores JSON files, including metadata and embeddings.
- **`Moteur de Recherche`**: Contains all functionalities related to the search engine, including embeddings and similarity computations.
- **`Fichier Total Run`**: Consolidates all functions for data extraction, NER, JSON creation, metadata embedding, and storage.
- **`P001`**: Patient folder used for testing purposes.

---

### [Link to Project Repository](https://github.com/ZinebAissaoui/Projet_S2D) 