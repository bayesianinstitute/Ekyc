
---

# eKYC Application

This eKYC (Electronic Know Your Customer) application is designed to perform identity verification using face recognition and OCR. It allows users to upload their ID card images and face images for verification.

## Features

- Registration using ID card.
- Face verification against the uploaded ID card using DeepFace and OCR using  Easy-ocr, Keras-ocr, and PaddleOCR are based on CRNN.
- Extraction of information from the ID card using OCR.
- Storage of verified user records in a MySQL database.

## High-Level Architecture

![High-Level Architecture](doc/high-level.png)

## Demo

Click the image below to watch a demo of the eKYC application:

[![eKYC Demo](doc/high-level.png)](https://drive.google.com/file/d/1-b8KCyQX6z13nLr--tmX4n3F4_Rlzsi9/view?usp=sharing)


## Requirements

- Python 3.8
- MySQL (for local development)

## Installation

1. Clone this repository:

   ```
   git clone https://github.com/yourusername/eKYC.git
   ```

2. Navigate to the project directory:

   ```
   cd eKYC
   ```

3. Install dependencies:

   ```
   pip install -r requirements.txt
   ```

4. Set up MySQL locally:

   - **Windows**: Download and install [MySQL Community Server](https://dev.mysql.com/downloads/mysql/).
   - **Mac**: Install MySQL using [Homebrew](https://brew.sh/):

     ```
     brew install mysql
     ```

   - **Linux**: Install MySQL using your distribution's package manager (e.g., `apt` for Ubuntu):

     ```
     sudo apt update
     sudo apt install mysql-server
     ```

5. Start the MySQL service:

   - **Windows**: Start the MySQL service from the Services application.
   - **Mac/Linux**: Start the MySQL service using the command:

     ```
     sudo service mysql start
     ```

6. Configure the MySQL connection details in the `.streamlit/secrets.toml` file.
    ```
    [mysql]
    host = "localhost"
    user = "root"
    password = ""
    database = "ekyc"
    ```

7. Run the application:

   ```
   streamlit run app.py
   ```

## Usage

1. Launch the application by running `streamlit run app.py`.
2. Select the ID card type (e.g., PAN) from the sidebar.
3. Upload the ID card image and the corresponding face image.
4. The application will perform face verification and extract information from the ID card.
5. If the verification is successful and the user is not a duplicate, their information will be stored in the database.

