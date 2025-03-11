# 🚀 MinIO Object Storage for HPE Firmware Log Management

## 📌 Overview
This project leverages **MinIO**, an open-source **object-level storage** solution, deployed using **Docker**. It is designed to efficiently store and retrieve **firmware update logs** collected from **HPE Client Servers**. The stored logs are later accessed by the HPE Server for evaluating the success of firmware updates.

## 🏗️ Project Workflow
1. **Bucket Creation** – A MinIO bucket is created to store log files.
2. **Log Storage** – Firmware log ZIP files from HPE Client Servers are uploaded to the bucket.
3. **Data Retrieval** – HPE Servers retrieve log files from the bucket for analysis.

## 📂 Notebooks Included
The project consists of **3 Jupyter notebooks**, each performing a specific role:

| Notebook | Function |
|----------|----------|
| `BucketCreation.ipynb` | Creates a MinIO bucket |
| `BucketPopulation.ipynb` | Uploads firmware log files to the bucket |
| `BucketRetrieval.ipynb` | Retrieves log files for evaluation |

## 🔒 Security & Best Practices
The implementation follows strict **software engineering principles**, ensuring:
✅ **Principle of least privilege** to minimize security risks.  
✅ **Clear variable naming and documentation** for maintainability.  
✅ **Abstraction of confidential credentials** for enhanced security.  
✅ **Strong networking security** to control access permissions.  

## 🛠️ Environment Configuration
To run this project, provide a `.env` file with the following syntax:

```ini
MINIO_ENDPOINT=<ip_address:port>
MINIO_ACCESS_KEY=<access_key>
MINIO_SECRET_KEY=<secret_key>
MINIO_SECURE=<True/False>
```

Ensure that `.env` is **excluded from version control** for security reasons.

## 🚀 Getting Started
### 1️⃣ Install & Run MinIO using Docker
```sh
docker run -p 9000:9000 -p 9000:9000 \
  --name minio \
  -e "MINIO_ROOT_USER=<username>" \
  -e "MINIO_ROOT_PASSWORD=<password>" \
  -v /data/minio:/data \
  minio/minio server /data --console-address ":9090"
```
### 2️⃣ Set Up Environment Variables
Create a `.env` file as described above.

### 3️⃣ Run Jupyter Notebooks
```sh
jupyter notebook
```
Execute the notebooks in the following order:
1️⃣ **BucketCreation.ipynb**  
2️⃣ **BucketPopulation.ipynb**  
3️⃣ **BucketRetrieval.ipynb**  

## 🎯 Conclusion
This project provides a **secure, scalable, and efficient** method for storing and retrieving HPE firmware logs using MinIO. It ensures high **security standards**, follows **best coding practices**, and enables seamless **firmware update evaluation**.

---
**Author:** *Darshan S M*  
**License:** MIT  

