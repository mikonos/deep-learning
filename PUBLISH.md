# Publishing to GitHub and skills.sh

## Step 1: Publish to GitHub

1. **Create a new repository on GitHub**
   - Log in to GitHub → New repository
   - Suggested repo name: `deep-learning` or `skill-deep-learning`
   - Set to Public; optionally check "Add a README" (though it may conflict with the local README — recommended to skip and use the existing local file)
   - After creation, note the repo URL, e.g.: `https://github.com/<your-username>/deep-learning.git`

2. **Initialize Git and push** (run in the `open-source/deep-learning` directory):

   ```bash
   cd "/path/to/open-source/deep-learning"

   git init
   git add .
   git commit -m "Initial release: deep-learning skill for Zettelkasten"
   git branch -M main
   git remote add origin https://github.com/<your-username>/deep-learning.git
   git push -u origin main
   ```

3. **Complete repository metadata**
   - On the GitHub repo page → About → Edit:
     - **Description**: `Deep reading skill for Zettelkasten: structure + atomic + method + index notes (Adler, Feynman, Luhmann). Cursor / skills.sh`
     - **Topics**: `zettelkasten`, `deep-reading`, `cursor`, `skills`, `knowledge-management`

---

## Step 2: Publish to skills.sh

1. **Installation command**  
   skills.sh installs from GitHub repositories. Users run:
   ```bash
   npx skills add <your-username>/deep-learning
   ```
   For example, if your GitHub username is `mikonos`:
   ```bash
   npx skills add mikonos/deep-learning
   ```

2. **Get listed on the skills.sh directory**
   - Go to [skills.sh](https://skills.sh)
   - If the platform has a "Submit skill" / "Add skill" entry, submit your repo URL (e.g. `mikonos/deep-learning`)
   - If no submission form exists, keep the repo Public with proper topics — it may be automatically indexed or manually curated later

3. **No build step required**  
   The platform reads `SKILL.md` and README directly from your GitHub repository.

---

## Step 3: Future Updates

After modifying files in this directory, run in the `deep-learning` folder:

```bash
git add .
git commit -m "Describe your changes"
git push
```

Once GitHub is updated, skills.sh will pull the latest version per its platform policy; users can reinstall or update to get the new content.
