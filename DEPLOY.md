# Deploy to GitHub Pages

These pages are static HTML, so GitHub Pages hosts them for free and renders them
exactly as designed. Two ways to do it — pick one.

## Option A — the web UI (no command line)

1. **Create a repository** in your district GitHub organization, e.g. `ai-infrastructure-lab`.
   Make it **Public** (the student content isn't sensitive, and public repos get
   free Pages). Keep the staff-only docs OUT of this repo.
2. **Upload the files.** On the repo page: **Add file → Upload files**, drag in
   `index.html`, `progression.html`, `modules.html`, `workbench.html`,
   `documentation.html`, `pathway.html`, `certifications.html`, `documentation-guide.html` (and optionally this `DEPLOY.md` / `README.md`), then
   **Commit changes**.
3. **Turn on Pages.** Go to **Settings → Pages**. Under **Build and deployment**,
   set **Source = Deploy from a branch**, **Branch = `main`**, **Folder = `/ (root)`**,
   then **Save**.
4. **Wait ~1 minute**, refresh the Settings → Pages screen, and copy the published
   URL. It looks like `https://<your-org>.github.io/ai-infrastructure-lab/`.
5. **Open it** — you should land on the Hub. Click through the nav and the module
   cards to confirm the links work, then share the URL with students.

## Option B — git command line

```
# from inside the folder with the .html files
git init
git add index.html progression.html modules.html workbench.html documentation.html pathway.html certifications.html documentation-guide.html
git commit -m "Add AI Infrastructure Lab student site"
git branch -M main
git remote add origin https://github.com/<your-org>/ai-infrastructure-lab.git
git push -u origin main
```
Then do step 3 above (Settings → Pages) to turn Pages on.

## Notes
- **Landing page:** GitHub Pages serves `index.html` at the root automatically, so
  the Hub is the front door. Nothing else to configure.
- **Updating a page:** edit the file in the repo (or re-upload it) and commit —
  Pages redeploys in about a minute. This is also a nice live example of the
  git → GitHub workflow students learn in the Workbench module.
- **Custom domain (optional):** Settings → Pages → Custom domain, if the district
  wants something like `ai-lab.southfayette.org` (needs a DNS record from IT).
- **Private instead of public:** private-repo Pages requires a paid GitHub plan
  (or the right org tier). For non-sensitive student content, a public repo is the
  simplest free path; keep staff docs in a separate private repo.
