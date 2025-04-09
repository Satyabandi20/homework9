# 🚀 Project: Secure QR Code API with CI/CD

This project is a FastAPI-based web service that lets users generate, view, and delete QR codes securely. Alongside the backend API, the project includes a complete CI/CD pipeline with GitHub Actions to automate testing, Docker builds, and vulnerability scanning.

---

## 🔧 What It Does

- **Generate QR Codes:**  
  Users can generate custom QR codes (with color, size, etc.).

- **Manage QR Codes:**  
  List all saved QR codes or delete specific ones.

- **Secured API Access:**  
  Endpoints are protected using OAuth2 password-based authentication.

- **CI/CD Pipeline:**  
  The project builds and tests itself on every push using GitHub Actions. Docker image gets built and scanned using Trivy before pushing to Docker Hub.

---

## ✅ Key Fixes & Enhancements

1. **Spelling Fixes:**  
   Corrected minor typos across files for better clarity and consistency.

2. **Auth Setup in Tests:**  
   Solved test failures caused by missing credentials by correctly loading `ADMIN_USER` and `ADMIN_PASSWORD` in both code and CI.

3. **Duplicate QR Code Handling:**  
   API now returns `409 Conflict` if a QR code for the same URL already exists.

4. **Docker Tagging Issues:**  
   Corrected the Docker image tag format to include the right Docker Hub path (`docker.io/satyabandi20/...`).

5. **Trivy Scan Failures:**  
   Added `TRIVY_TOKEN` to fix rate limit issues and ensured Trivy scans run smoothly in CI.

6. **Security Updates:**  
   - Upgraded `python-jose` to `3.4.0` to patch a critical security issue.  
   - Downgraded `pyasn1` to `0.4.8` for compatibility.  
   - Locked `starlette` to `0.37.2` to match FastAPI's dependency requirements.

---

## 🛠️ Requirements

- Python 3.10+
- Docker
- (Optional) Trivy CLI for manual scans

---

## ⚙️ How to Use

### 1. Clone & Setup

```bash
git clone <your-repo-url>
cd homework9
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### 2. Run the App

```bash
mkdir -p qr_codes
docker compose up --build
```

### 3. Run Tests

```bash
pytest
```

### 4. Access the API Docs

Open [http://localhost/docs](http://localhost/docs) in your browser.

---

## 👤 Maintainer

**Satya Bandi**  
Feel free to connect if you're reviewing the code or planning to contribute.
