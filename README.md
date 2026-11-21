# HackJam '26 Contributor Wall

The demo repo for the **Git/GitHub for Hackathons** workshop. Add yourself to the wall by opening a pull request. Once it's merged, your card shows up on the site.

## Add yourself

### Option A: Terminal

1. Click **Fork** at the top of this page.
2. Clone **your fork** and go into it:
   ```bash
   git clone https://github.com/<your-username>/hackjam-git-demo.git
   cd hackjam-git-demo
   ```
3. Make a branch:
   ```bash
   git switch -c add-<your-username>
   ```
4. Create a file named `_contributors/<your-username>.md` with this inside:
   ```markdown
   ---
   name: "Your Name"
   github: "your-username"
   school: "Your School"
   message: "What you're building or excited about"
   ---
   ```
5. Commit and push:
   ```bash
   git add _contributors/<your-username>.md
   git commit -m "Add <your name> to the wall"
   git push -u origin add-<your-username>
   ```
6. On GitHub, click **Compare & pull request**, then **Create pull request**.

### Option B: Browser only

If Git isn't set up on your laptop yet:

1. Click **Fork** at the top of this page.
2. In your fork, open the `_contributors` folder and click **Add file → Create new file**.
3. Name it `<your-username>.md` and paste in the template from step 4 above.
4. Click **Commit changes**, choose **Create a new branch**, then **Propose changes**.
5. Click **Create pull request**.

## Rules

- **Only add your own file.** Don't edit anyone else's file, or anything outside `_contributors/`.
- **Keep the quotes** around every value in the template. A missing quote can stop the site from updating.
- Keep it friendly. This goes up on the projector.

## For the presenters

Merge every open PR into the default branch:

```bash
gh pr list --json number -q '.[].number' | xargs -I{} gh pr merge {} --merge
```

The **Pick someone** button on the site highlights a random contributor.
