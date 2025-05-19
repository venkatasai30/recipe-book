
# Git Practice Project: Recipe Manager — Study Notebook

## 1. Create a New Repo on GitHub
- **Name:** `recipe-book`
- **Description:** A collection of simple recipes categorized by meals
- **Settings:** Public repo, no README initially
- Create the repo on GitHub website.

## 2. Clone the Repo Locally

```bash
cd /your/folder/path
git clone https://github.com/<your-username>/recipe-book.git
cd recipe-book
```

- This downloads your empty repo to local machine.
- You’ll work inside this folder.

## 3. Create Folder Structure & Files

```bash
mkdir breakfast lunch dinner

cd breakfast
touch oats.md

cd ../lunch
touch biryani.md

cd ../dinner
touch pasta.md
```

- Organizes recipes by meal type.
- Empty markdown files to add recipes.

## 4. Add Initial Content to Markdown Files

Example: `breakfast/oats.md`

```markdown
# Oats Recipe

## Ingredients
- 1/2 cup oats
- 1 cup milk
- Honey
- Fruits

## Steps
1. Boil oats in milk for 5 minutes.
2. Add honey and fruits.
3. Serve warm.
```

Do similar for:

- `lunch/biryani.md` (add biryani recipe)
- `dinner/pasta.md` (add pasta recipe)

## 5. Initialize Git Repo (if not done)

```bash
cd recipe-book
git init
```

- Creates a new `.git` folder to track changes.

## 6. Stage and Commit Initial Files

```bash
git add .
git commit -m "Initial commit with folder structure and recipes"
```

- `git add .` stages all changes.
- Commit saves a snapshot with message.

## 7. Link Remote Repo and Push

If not linked yet:

```bash
git remote add origin https://github.com/<your-username>/recipe-book.git
git branch -M main
git push -u origin main
```

- Connects local repo to GitHub.
- Pushes your commit to GitHub main branch.

## 8. Create & Work on Feature Branches

- For breakfast recipes:

```bash
git checkout -b breakfast-recipes
# edit oats.md (or add new files)
git add breakfast/oats.md
git commit -m "Update oats recipe"
git push -u origin breakfast-recipes
```

- For lunch recipes:

```bash
git checkout main
git checkout -b lunch-recipes
# edit biryani.md
git add lunch/biryani.md
git commit -m "Add biryani recipe"
git push -u origin lunch-recipes
```

## 9. Merge Feature Branches into Main

```bash
git checkout main
git merge breakfast-recipes
git merge lunch-recipes
```

- Resolve conflicts if any.
- After fixing conflicts:

```bash
git add <conflicted-file>
git commit
```

## 10. Add README.md

Create a `README.md` in repo root:

```markdown
# Recipe Book

A simple collection of recipes.

## Contents
- [Oats](breakfast/oats.md)
- [Biryani](lunch/biryani.md)
- [Pasta](dinner/pasta.md)
```

Then:

```bash
git add README.md
git commit -m "Add README with recipe list"
git push
```

## 11. Add a `.gitignore`

```bash
touch .gitignore
echo "*.log" >> .gitignore
echo "*.DS_Store" >> .gitignore
git add .gitignore
git commit -m "Add .gitignore to exclude logs and system files"
git push
```

- Prevent unwanted files from being tracked.

## 12. Add Tags for Versioning

```bash
git tag v1.0
git push origin v1.0
```

- Useful to mark release points in project history.

# What You Practiced

- Cloning a repo
- Creating folder structure & files
- Writing Markdown files
- Git init, add, commit, push
- Branching & merging
- Handling merge conflicts
- Using `.gitignore`
- Creating tags and versioning

# Bonus Study Tips

- Use `git status` frequently to check current state.
- Use `git log --oneline` to see commit history quickly.
- Practice switching branches with `git checkout`.
- Try `git diff` to see changes before staging.
- Explore GitHub’s Pull Requests for merging branches.

