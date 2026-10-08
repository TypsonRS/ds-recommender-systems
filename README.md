# Introduction to Recommender Systems

A hands-on introduction to recommender systems. You will build content-based and collaborative filtering recommenders, generate recommendations for new users, and measure how well those recommenders perform. The collaborative filtering notebooks use [scikit-surprise](https://surprise.readthedocs.io/en/stable/), a Python library for building and analysing recommenders that work with [explicit rating](https://mirumee.com/blog/the-difference-between-implicit-and-explicit-data-for-business) data.

## Learning Objectives

By the end of this repository, you should be able to:

- Build a content-based recommender that ranks items by the cosine similarity of their features.
- Apply TF-IDF to turn item descriptions into vectors and generate similarity-based recommendations.
- Implement collaborative filtering with K-Nearest-Neighbors and matrix factorisation (SVD) using scikit-surprise.
- Generate top-N recommendations for a new user from a trained collaborative filtering model.
- Calculate offline evaluation metrics (MAE, RMSE, hit rate, coverage) to measure recommender quality.
- Compare content-based and collaborative filtering approaches and select one for a given scenario.

## Learning Path

Work through the notebooks in this order:

| File / Folder | Description |
|---|---|
| [**01 - Content-Based Recommender**](01_content_based.ipynb) | Rank items by cosine similarity over their features, then build a text-based recommender with TF-IDF. |
| [**02 - Exercise: Most-Popular Movie Recommender**](02_exercise_most_popular.ipynb) | Explore the ratings data and build a popularity baseline from rating counts. |
| [**03 - Collaborative Filtering: Similarity**](03_collaborative_filtering_similarity.ipynb) | Predict ratings with K-Nearest-Neighbors (user-based and item-based) using scikit-surprise. |
| [**03 - Collaborative Filtering: Matrix Factorization**](03_collaborative_filtering_matrix_factorisation.ipynb) | Predict ratings with Singular Value Decomposition (SVD) and tune it with grid search. |
| [**03 - Exercise: Collaborative Filtering Recommender**](03_exercise_collaborative_filtering.ipynb) | Build your own collaborative filtering movie recommender with scikit-surprise. |
| [**04 - Recommender Evaluation**](04_recommender_evaluation.ipynb) | Measure recommenders with offline metrics (MAE, RMSE, hit rate, coverage) and online methods (A/B tests). |

### Additional Folders and Files

| File / Folder | Description |
|---|---|
| [**Data**](data/) | Fish feature data and user-item rating datasets used across the notebooks. |
| [**Images**](images/) | Diagrams referenced in the notebooks. |
| [**Solutions**](solutions/) | Reference solutions. |
| [**pyproject.toml**](pyproject.toml) | Project configuration and dependencies. |
| [**uv.lock**](uv.lock) | Dependency lock file. |

## Setup

> [!NOTE]
> Throughout these steps, text in angle brackets like `<repo-name>` is a
> **placeholder**. Replace it, including the `< >` brackets, with your own
> value. For example, `cd <repo-name>` becomes `cd ds-recommender-systems`.

### 1. Create the Repository from the Template

Click **Use this template** on GitHub.

When creating the repository:

- Set yourself as the **Owner**
- Choose a repository name
- Disable **Include all branches**
- Click **Create repository**

> [!IMPORTANT]
> If you are working in pairs or groups, only **one person** should complete this step.

---

### 2. Add Collaborators (Pairs/Groups Only)

If working with teammates:

1. Open the repository on GitHub
2. Go to **Settings → Collaborators**
3. Add your teammates as collaborators
4. Share the repository link with your team

Teammates should accept the invitation before continuing.

---

### 3. Clone the Repository

Copy the SSH URL from the **Code** button on GitHub, then run:

```bash
git clone <copied-ssh-url>
```

The copied SSH URL will look like `git@github.com:<your-username>/<repo-name>.git`.

---

### 4. Move into the Project Folder and Install Dependencies

This installs all dependencies and creates a virtual environment in (`.venv/`).

```bash
cd <repo-name>
uv sync
```

> [!TIP]
> `uv sync` installs scikit-surprise from a prebuilt wheel on macOS, Linux, and 64-bit Windows, so you do not need any C++ build tools.

---

### 5. Open the Notebooks

> [!NOTE]
> Make sure you open VS Code from the project root so it automatically detects the environment created by `uv sync`.

Launch VS Code in the project root folder:

```bash
code .
```

Then open a notebook and select the Python environment created by `uv sync` as the kernel.

## References & Further Reading

- [**Surprise documentation**](https://surprise.readthedocs.io/en/stable/): Official docs for the scikit-surprise recommender library used in the collaborative filtering notebooks.
- [**scikit-learn TfidfVectorizer**](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html): Reference for the TF-IDF vectorizer used in the content-based notebook.
- [**Google: Recommendation Systems course**](https://developers.google.com/machine-learning/recommendation): A short course covering content-based filtering, matrix factorisation, and deep recommenders.
- [**Implicit vs explicit data**](https://mirumee.com/blog/the-difference-between-implicit-and-explicit-data-for-business): Why the type of feedback you collect shapes the recommender you can build.
