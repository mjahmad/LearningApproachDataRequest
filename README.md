# Public Data Request Form

This is an editable static HTML form designed for GitHub Pages. It replicates the structure of the original Google Form for requesting access to the data used in:

> “The Untold Impact of Learning Approaches on Software Fault-Proneness Predictions: An Analysis of Temporal Aspects”

## Files

- `index.html` — the public form.
- `style.css` — visual styling.
- `thank-you.html` — confirmation page after submission.

## Step 1 — Create a Formspree endpoint for email notifications

GitHub Pages only hosts static files. It does not process form submissions or send emails. Use Formspree as the form backend.

1. Go to Formspree.
2. Create an account using the email address where you want to receive notifications.
3. Create a new form/project.
4. Copy the endpoint. It will look like:

```text
https://formspree.io/f/abcxyzpq
```

5. Open `index.html`.
6. Find this line:

```html
<form class="form-card" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

7. Replace it with your real endpoint:

```html
<form class="form-card" action="https://formspree.io/f/abcxyzpq" method="POST">
```

8. Save the file.

## Step 2 — Upload to GitHub

Option A: upload using the GitHub website.

1. Open your GitHub repository.
2. Click **Add file** → **Upload files**.
3. Drag in these files:
   - `index.html`
   - `style.css`
   - `thank-you.html`
4. Click **Commit changes**.

Option B: upload using command line.

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
cd YOUR_REPO
cp /path/to/index.html .
cp /path/to/style.css .
cp /path/to/thank-you.html .
git add index.html style.css thank-you.html
git commit -m "Add public data request form"
git push
```

## Step 3 — Enable GitHub Pages

1. In the repository, go to **Settings**.
2. Click **Pages** on the left.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Choose:
   - Branch: `main`
   - Folder: `/root`
5. Click **Save**.

Your form should appear at:

```text
https://YOUR_USERNAME.github.io/YOUR_REPO/
```

## Step 4 — Test the form

1. Open your GitHub Pages URL.
2. Submit a test request using your own email.
3. Check your email inbox.
4. Check the Formspree dashboard to confirm the submission was saved.
5. If Formspree asks you to confirm the form/email the first time, complete that confirmation.

## Step 5 — Replace the old Google Form link where possible

Because a new GitHub Pages URL cannot take over the old Google Forms URL unless the deleted Google Form is restored, put the new GitHub Pages URL in:

- your project GitHub README,
- your personal/lab website,
- OSF/Zenodo/data repository page,
- paper supplementary material,
- publisher correction/erratum if allowed.

## Editing the questions

Open `index.html` in any editor. Each question is inside a `<section class="question block">...</section>` block. Edit the text between the labels without changing the `name="..."` attributes unless you also want the submitted field names to change in your email notification.
