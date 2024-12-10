**Enhanced OCR System with Gemini AI**  

This repository contains an advanced OCR (Optical Character Recognition) system that integrates traditional OCR methods with Google Gemini AI to provide highly accurate text extraction, refinement, and translation. The system is built using a combination of Python scripts, a Jupyter Notebook, and a GUI application.  

The system aims to provide users with an end-to-end solution for extracting, refining, and translating text from images, such as scanned documents, invoices, or receipts.  

---

## **Table of Contents**  
1. [Features](#features)  
2. [Project Structure](#project-structure)  
3. [Installation](#installation)  
4. [Usage](#usage)  
5. [File Descriptions](#file-descriptions)  
6. [Algorithm](#algorithm)  
7. [Key Functions](#key-functions)  
8. [Screenshots](#screenshots)  
9. [API Key Management](#api-key-management)  
10. [Contributing](#contributing)  
11. [License](#license)  

---

## **Features**  
- **Multi-Layer OCR**: Uses both EasyOCR and Google Gemini AI to extract text from images.  
- **AI-Powered Text Refinement**: Refines text to improve grammar, remove extra spaces, and enhance readability.  
- **Translation Support**: Translates both raw OCR text and refined text into a user-specified language.  
- **Bounding Box Annotation**: Visualizes detected text with bounding boxes on images.  
- **Interactive GUI**: A user-friendly graphical interface for file selection, OCR processing, and text display.  
- **Fuzzy Text Matching**: Uses fuzzy matching to map OCR-extracted words to the refined text.  

---

## **Project Structure**  

```
📦 Enhanced-OCR-System  
 ┣ 📜 Gemini_OCR_SDK.ipynb        # Jupyter Notebook for image text extraction using Gemini  
 ┣ 📜 Gemini_OCR_SDK.py           # GUI-based application for OCR, text refinement, and translation  
 ┣ 📜 Gemini_OCR_request.py      # Standalone script for direct Gemini API requests  
 ┣ 📜 requirements.txt            # List of required Python libraries  
 ┗ 📜 README.md                   # Project description and usage guide  
```  

---

## **Installation**  

### **1. Clone the Repository**  
```bash
git clone https://github.com/your-username/Enhanced-OCR-System.git
cd Enhanced-OCR-System
```

### **2. Set Up a Virtual Environment** (Optional but recommended)  
```bash
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
```

### **3. Install Required Packages**  
```bash
pip install -r requirements.txt
```

**Required Libraries**  
- `google-generativeai`  
- `easyocr`  
- `opencv-python`  
- `pillow`  
- `tkinter` (built-in for Python)  
- `fuzzywuzzy`  
- `python-Levenshtein` (required for fuzzywuzzy)  
- `requests`  
- `googletrans`  

---

## **Usage**  

### **1. Run the Jupyter Notebook**  
To test the system using a Jupyter Notebook:  
```bash
jupyter notebook Gemini_OCR_SDK.ipynb
```
This notebook demonstrates how to extract text using the Gemini AI API.  

---

### **2. Launch the GUI Application**  
Run the following command to start the GUI-based application:  
```bash
python Gemini_OCR_SDK.py
```
**Steps to Use the GUI**  
1. Click **"Select Image and Process"**.  
2. Choose an image file (JPG, JPEG, PNG).  
3. The following will be displayed:  
   - **Bounding Box Annotation**: Text regions on the image.  
   - **Extracted OCR Text**: Initial raw text from EasyOCR.  
   - **Refined Text**: Enhanced version of the text from Gemini AI.  
   - **Translated Text**: Translated text in the language you choose.  

---

### **3. Run the Standalone API Script**  
To extract text directly from the Gemini API:  
```bash
python Gemini_OCR_request.py
```
Edit the `image_path` variable in the script to point to your image file.  

---

## **File Descriptions**  

1. **Gemini_OCR_SDK.ipynb**  
   - Demonstrates how to extract text from images using Gemini AI.  
   - Displays results directly in a Jupyter Notebook.  

2. **Gemini_OCR_SDK.py**  
   - A GUI-based application to process images, extract and refine text, and display bounding boxes.  
   - Uses Tkinter for the interface.  

3. **Gemini_OCR_request.py**  
   - Directly calls the Gemini API for text extraction.  
   - Useful for testing the Gemini API with custom images.  

---

## **Algorithm**  

1. **Image Preprocessing**  
   - Convert image to grayscale, apply denoising, and threshold the image for clarity.  

2. **Text Detection (EasyOCR)**  
   - Detects bounding boxes and extracts text using EasyOCR.  

3. **Gemini AI Refinement**  
   - Sends extracted text to Gemini AI for refinement.  
   - Refines grammar, sentence structure, and readability.  

4. **Fuzzy Matching**  
   - Compares EasyOCR's extracted text with Gemini AI's refined text.  
   - Matches text to the bounding boxes using fuzzy logic.  

5. **Translation**  
   - Translates both extracted and refined text into a user-specified language.  

---

## **Key Functions**  

| **File**            | **Function**                | **Description**                                      |
|---------------------|---------------------------|-----------------------------------------------------|
| `Gemini_OCR_SDK.py`  | `preprocess_image`        | Preprocess image for better OCR results.             |
|                     | `easyocr_text_detection`  | Extracts text and bounding boxes using EasyOCR.     |
|                     | `gemini_refine_text`      | Refines text using Gemini AI.                        |
|                     | `translate_text`          | Translates text using Google Translate.              |
|                     | `fuzzy_match_word`        | Matches OCR text to refined text using fuzzy logic.  |
|                     | `process_image`           | Complete pipeline for image processing.             |

---

## **Screenshots**  
![IMG-20241209-WA0003](https://github.com/user-attachments/assets/1df52cba-edb9-4839-be5c-b367f09758a7)

---

## **API Key Management**  

1. Open `Gemini_OCR_SDK.py` and `Gemini_OCR_request.py`.  
2. Replace the **API Key** with your Gemini API Key:  
   ```python
   genai.configure(api_key="your_gemini_api_key_here")
   ```

**Security Tip**: Avoid exposing API keys in public repositories. Use environment variables or a `.env` file instead.  

---

## **Contributing**  

1. Fork the repository.  
2. Create a new branch: `git checkout -b feature/your-feature-name`.  
3. Make your changes and commit them: `git commit -m 'Add feature'`.  
4. Push to the branch: `git push origin feature/your-feature-name`.  
5. Create a pull request.  

---

## **License**  

This project is licensed under the MIT License.  

---
