# STEM Document Deconstructor (BYOP)

## Problem Statement
Visually impaired students in STEM fields face immense challenges with heavily formatted textbook pages where traditional screen readers fail to differentiate between dense text paragraphs, mathematical charts, and diagrams. 

This project solves this by using a Computer Vision pipeline to automatically segment a document page, extract distinct structural elements, and classify them as either readable "Text" or "Figures/Diagrams" so accessibility tools can process them correctly.

## Technologies Used (Syllabus Coverage)
- **Image Processing:** OpenCV (Grayscale conversion, Gaussian Blurring)
- **Edge Detection:** Canny Edge Detection
- **Morphological Operations:** Dilation with rectangular kernels to group text structures
- **Segmentation:** Contour mapping and bounding box generation
- **Classification:** Tesseract OCR for text vs. figure validation

## Setup & Installation

**1. Clone the repository:**
\`\`\`bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git
cd YOUR-REPO-NAME
\`\`\`

**2. Install Python Dependencies:**
This project requires Python 3.8+. Install the required libraries using pip:
\`\`\`bash
pip install opencv-python numpy pytesseract
\`\`\`

**3. Install Tesseract OCR Engine (Required):**
You must install the Tesseract system binary for the classification to work.
- **Windows:** Download and install from [UB-Mannheim Tesseract](https://github.com/UB-Mannheim/tesseract/wiki). *(Note: Ensure the Tesseract path is added to your System Environment Variables).*
- **Linux (Ubuntu):** `sudo apt-get install tesseract-ocr`
- **Mac:** `brew install tesseract`

## How to Run the Project
This project is fully executable via the command line interface (CLI). No GUI setup is required.

Run the following command from the root of the repository, passing your target image via the `-i` or `--image` argument:

\`\`\`bash
python deconstruct.py --image sample_page.jpg
\`\`\`

**Expected Output:**
The script will output the processing logs to the terminal, tallying the number of text blocks and figures found. It will automatically generate an `output/` folder and save the fully annotated, color-coded image inside it.
