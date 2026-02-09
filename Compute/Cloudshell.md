# ☁️ Google Cloud Shell – Quick Start & Usage Guide

Google **Cloud Shell** is a browser-based command-line environment that makes it easy to manage Google Cloud resources without local setup.

---

## 🚀 What Cloud Shell Provides

Cloud Shell comes preconfigured with everything you need:

* **Temporary Compute Engine VM**
* **Browser-based command-line access**
* **5 GB persistent disk storage** (`$HOME` directory)
* **Pre-installed Cloud SDK & tools**
* **Built-in authentication** for your Google Cloud resources
* **Web preview** for running web apps

### 🧰 Pre-installed Tools

| Tool             | Purpose                                       |
| ---------------- | --------------------------------------------- |
| `gcloud`         | Manage Compute Engine & Google Cloud services |
| `gcloud storage` | Work with Cloud Storage buckets & objects     |
| `kubectl`        | Manage Kubernetes & GKE clusters              |
| `bq`             | Query BigQuery datasets                       |

### 🧪 Supported Languages

* Java
* Go
* Python
* Node.js
* PHP
* Ruby

---

## 🪣 Create a Cloud Storage Bucket (via gcloud)

Create a globally unique Cloud Storage bucket:

```bash
gcloud storage buckets create gs://singarajtestnew
```

### 📄 Upload a File to the Bucket

```bash
gcloud storage cp test.txt gs://singarajtestnew
```

---

## 💾 Creating a Persistent State in Cloud Shell

Cloud Shell resets the VM periodically, but anything inside **`$HOME`** persists. To maintain configuration across sessions, follow these steps.

### 1️⃣ Define Environment Variables

```bash
INFRACLASS_REGION=us-east1
echo $INFRACLASS_REGION
```

### 2️⃣ Create a Configuration Directory & File

```bash
mkdir infraclass
touch infraclass/config
```

### 3️⃣ Save Variables to Config File

```bash
echo INFRACLASS_REGION=$INFRACLASS_REGION >> ~/infraclass/config

INFRACLASS_PROJECT_ID=qwiklabs-gcp-01-084d27d2494b
echo INFRACLASS_PROJECT_ID=$INFRACLASS_PROJECT_ID >> ~/infraclass/config
```

### 4️⃣ Load the Configuration

```bash
source infraclass/config
echo $INFRACLASS_PROJECT_ID
```

---

## 🔁 Auto-load Configuration on Shell Startup

To ensure your variables are always available when Cloud Shell starts:

### 1️⃣ Edit `.profile`

```bash
vi ~/.profile
```

### 2️⃣ Add the Following Line

```bash
source infraclass/config
```

### 3️⃣ Save & Exit (vi)

```text
:wq
```

### 4️⃣ Verify

```bash
echo $INFRACLASS_PROJECT_ID
```

---

## ✅ Best Practices

* Store scripts and configs in `$HOME`
* Avoid placing sensitive data in config files
* Use IAM roles instead of hardcoded credentials
* Regularly clean unused resources

---

## 📚 References

* Google Cloud Shell Documentation
* Google Cloud SDK (`gcloud`) Docs
* Cloud Storage Documentation

---

✨ Happy Cloud Building!
