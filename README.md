# LandIQ Project

A web application that scrapes permitting data, stores it in MongoDB, and provides API access for querying the data.

---

## 📁 Project Structure
```
LandIQ/
|
├── .env                # Environment variables (MongoDB URI)
├── .gitignore          # Files and folders to ignore in Git
├── README.md           # Project documentation
├── requirements.txt    # Python dependencies
├── database/           # MongoDB connection setup
│   └── mongo_config.py  # MongoDB connection script
├── scraper/            # Web scraper scripts
│   └── scraper.py       # Web scraping logic
├── API/                # API setup (FastAPI or Flask)
└── utils/              # Utility functions (optional)
```

---

## 🔧 Installation Instructions

### 1. **Clone the Repository**
```bash
git clone https://github.com/yourusername/LandIQ.git
cd LandIQ
```

### 2. **Set Up Virtual Environment**
```bash
python3 -m venv venv
source venv/bin/activate  # For macOS/Linux
# For Windows: venv\Scripts\activate
```

### 3. **Install Required Dependencies**
```bash
pip install -r requirements.txt
```

### 4. **Configure Environment Variables**

1. Create a `.env` file in the project root directory.
2. Add your MongoDB connection string in the `.env` file:
   ```
   MONGODB_URI=mongodb+srv://<username>:<password>@landiq.w0p0x.mongodb.net/?retryWrites=true&w=majority&appName=LandIQ
   ```

### 5. **Test MongoDB Connection**

Run the MongoDB connection script to ensure the database connection is working:
```bash
python database/mongo_config.py
```
You should see:
```
Pinged your deployment. You successfully connected to MongoDB!
```

---

## 🚀 Running the Web Scraper

After setting up the connection, you can run the web scraper to collect data and store it in MongoDB.

```bash
python scraper/scraper.py
```

This will scrape permitting data and insert it into the **`LandIQ`** database in MongoDB.

---

## 🛠️ API Setup (Optional)

If you plan to expose the scraped data via API:

1. Navigate to the `API/` folder.
2. Create your API using **FastAPI** or **Flask**.
3. Run the API server:
   ```bash
   uvicorn API.app:app --reload  # For FastAPI
   # or
   python API/app.py  # For Flask
   ```

---

## 🔍 Branching Directions

To keep the development process organized, follow this branching strategy:

### 1. **Main Branches:**
- **`main`**: This is the production-ready branch. Code here should always be stable and deployable.
- **`develop`**: The integration branch where all features are combined before being pushed to `main`.

### 2. **Feature Branches:**
Each new feature or set of related tasks should be developed in its own branch. Use the following naming conventions:

- `feature/<feature-name>` for general features.
- `feature/<person-name>/<feature-name>` if you want to track who is working on what.

### Example Branches:
- `feature/evan/mongodb-setup` - For setting up MongoDB connection.
- `feature/alex/web-scraper` - For developing the web scraper.
- `feature/jordan/api-development` - For creating API endpoints.

### 3. **Workflow Steps:**

1. **Create a Feature Branch:**
   ```bash
   git checkout develop
   git pull origin develop
   git checkout -b feature/your-feature-name
   ```

2. **Make Changes and Commit:**
   ```bash
   git add .
   git commit -m "Describe your changes"
   ```

3. **Push Your Branch:**
   ```bash
   git push origin feature/your-feature-name
   ```

4. **Create a Pull Request:**
   - Open a PR from your feature branch to `develop`.
   - After review and approval, merge the PR.

5. **Merge `develop` into `main`:**
   Once all features are tested together in `develop`, create a PR to merge `develop` into `main`.

### 4. **Deleting Branches After Merging:**
To keep the repository clean, delete feature branches after merging:

- **Delete from GitHub:**
  After merging, click "Delete Branch" in the PR interface.

- **Delete Locally:**
  ```bash
  git branch -d feature/your-feature-name
  ```

- **Delete from Remote:**
  ```bash
  git push origin --delete feature/your-feature-name
  ```

---

## 🎓 Contributing
1. Fork the repository.
2. Create a new branch: `git checkout -b feature-branch`.
3. Commit your changes: `git commit -m "Add new feature"`.
4. Push to the branch: `git push origin feature-branch`.
5. Submit a pull request.

---

## 📅 License

This project is **proprietary**. All rights reserved. Unauthorized copying, modification, or distribution of this software is prohibited.

---

## 🚜 Contact

For any inquiries, please contact **Evan Tseng** at `evantseng@econ2-207-136-edu.int.colorado.edu`.

