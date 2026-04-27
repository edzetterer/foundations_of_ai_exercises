# 🔍 Foundations of Artificial Intelligence – Search Exercises
**University of Bremen · Institute for Artificial Intelligence · SS 2026**  
*Prof. Michael Beetz, Ph.D. · Dr. Michaela Kuempel, Sorin Arion*

---

## 📋 Contents

Under the exercises folder you can find the exercises and solutions for the exercises of the course. 
---

## 🍴 Getting Started — Fork this Repository First!

> **Students:** please **fork** this repo to your own GitHub account before cloning.  
> This way you have your own copy to work in, and you can submit improvements back via Pull Requests (see [Contributing](#-contributing) below).

New to GitHub? Here are some helpful links:

- 📖 [What is a fork?](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)
- 📖 [How to clone a repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)
- 📖 [GitHub Desktop (GUI, no terminal needed)](https://desktop.github.com/)
- 📖 [Git basics cheat sheet](https://education.github.com/git-cheat-sheet-education.pdf)

```bash
# After forking, clone YOUR fork:
git clone https://github.com/<your-username>/foundations_of_ai_exercises.git
cd foundations_of_ai_exercises
```

---

## 🚀 Three Ways to Run the Notebook

Choose whichever option suits you best — no programming setup required for options 1 and 2.

---

### Option 1 — Google Colab (easiest, no installation)

1. Go to [colab.research.google.com](https://colab.research.google.com)
2. Click **File → Upload notebook**
3. Upload `notebooks/search_exercises.ipynb`
4. Press **Shift + Enter** to run cells — you're done!

---

### Option 2 — Docker (recommended for a consistent environment)

> Requires [Docker Desktop](https://www.docker.com/products/docker-desktop/) (free).  
> Works on Windows, macOS, and Linux without any Python setup.

```bash
# 1. Clone your fork (see above)
# 2. Build and start the container:
cd docker
docker compose up --build

# If docker compose is not available, use:
docker-compose up --build

# Try with sudo if you get permission errors.
# 3. Open your browser and go to:
#    http://localhost:8888
#
# Your notebook is in the notebooks/ folder inside JupyterLab.
# All changes are automatically saved back to your local notebooks/ folder.

# 4. Stop the container when you are done:
docker compose down
```

If you don't have `docker compose` (older Docker versions), use:

```bash
docker build -t fai-exercises .
docker run -p 8888:8888 -v "$(pwd)/notebooks:/home/jovyan/work/notebooks" fai-exercises
```

---

### Option 3 — pip install (local Python)

> Requires Python 3.9 or newer. Check with `python --version`.

```bash
# 1. (Recommended) Create a virtual environment first:
python -m venv .venv

# Activate it:
# On macOS / Linux:
source .venv/bin/activate
# On Windows (PowerShell):
.venv\Scripts\Activate.ps1

# 2. Install dependencies:
pip install -r requirements.txt

# 3. Launch JupyterLab:
jupyter lab notebooks/search_exercises.ipynb
```

Your browser should open automatically at `http://localhost:8888`.  
If it doesn't, copy the URL printed in the terminal.

---

## 🗂️ Repository Structure

```
foundations_of_ai_exercises/
├── exercises/
    └──current_topic                     # The topic of the exercises, like search or logic
        └──notebooks/
           └── search_exercises.ipynb    # 🐍 Coding exercises
        └── exercises.md                 # ✏️  Worksheet (no solutions)
        └── solutions.md                 # Solutions   
├── docker
    └── docker-compose.yml
    └── Dockerfile                       
├── requirements.txt                     # Python dependencies
└── README.md                            # This file
```

---

## 🤝 Contributing

Found a typo? Have a better explanation? Want to add a new exercise?  
**Pull Requests are very welcome!** 🎉

Here is how:

1. Fork the repository (see [Getting Started](#-getting-started--fork-this-repository-first) above)
2. Create a new branch for your change:
   ```bash
   git checkout -b improve/clearer-bfs-hint
   ```
3. Make your changes and commit them:
   ```bash
   git add .
   git commit -m "Add clearer hint for BFS queue step"
   ```
4. Push to your fork:
   ```bash
   git push origin improve/clearer-bfs-hint
   ```
5. Open a Pull Request on GitHub — [here's how](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)

### Ideas for contributions

- 🧩 Add a new exercise (e.g. iterative deepening, bidirectional search)
- 📝 Improve explanations or hints in the notebook
- 🐛 Fix a bug or an error in the solutions
- 🌍 Translate exercises to German

All contributors will be acknowledged. Thank you for helping make this resource better for everyone! 🙌

---

## 📚 Further Reading

- [Russell & Norvig – Artificial Intelligence: A Modern Approach (Ch. 3)](https://aima.cs.berkeley.edu/)
- [A* Search visualized](https://www.redblobgames.com/pathfinding/a-star/introduction.html) — great interactive demo
- [BFS / DFS visualizer](https://visualgo.net/en/dfsbfs)

---

## 📄 License

This material is provided for educational purposes at the University of Bremen.  
Feel free to use and adapt it with attribution.
