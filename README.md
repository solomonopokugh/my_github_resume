
# Jekyll Resume Site Template

This template gives you a personal resume website, hosted for free on GitHub Pages. It's also a hands-on way to learn how a Jekyll site works. The demo content belongs to **Victor E. Huskie**, NIU's mascot. Your job is to replace it, piece by piece, with your own.

By the end you'll have:

- A home page that introduces you
- A **Curriculum Vitae** link in the menu that opens your resume PDF in a new tab
- A **Blog Posts** page for class reflections or project write-ups
- **Links** and **Contact** pages
- A live URL like `https://yourusername.github.io/your-repo-name/` that you can put on a resume or LinkedIn

You don't need any web development experience. Everything below can be done in your browser on GitHub. If you'd like a warm-up first, try GitHub's [GitHub Pages exercise](https://github.com/skills/github-pages).

## 🌮 Tech Tacos: build your website resume

This template is used for the "Build your website resume" session at **Tech Tacos**. Tech Tacos is a beginner-friendly tech meetup hosted by [71 North](https://71north.github.io/), NIU's Partnership Studio. Each Tuesday covers a different topic, from coding basics and GitHub to AI and emerging tech, with time to network and eat tacos.

- **Where:** 71 North Partnership Studio, Founders Memorial Library, 217 Normal Rd, DeKalb, IL
- **When:** Tuesdays, 5:00–7:00 PM, during the semester. Check [techtacos.org](https://techtacos.org) or the [NIU events calendar](https://calendar.niu.edu) for this semester's schedule.
- **Questions:** [71North@niu.edu](mailto:71North@niu.edu)

**Before the session**, to get the most out of your time:

1. Create a GitHub account with your NIU email ([Step 0](#step-0-get-a-github-account)).
2. Have a headshot photo ready. A phone photo against a plain wall is fine.
3. Have your resume saved as a PDF. If you don't have one yet, see [Step 5](#step-5-add-your-resume-pdf).

**During the session**, we'll work through Steps 1–7 together. You should leave with a live site you can link from your resume and LinkedIn. If you don't finish, the steps below let you pick up where you left off.

## What is Jekyll?

[Jekyll](https://jekyllrb.com/) is a *static site generator*. You write pages in Markdown, a simple text format, and Jekyll turns them into a complete HTML website. GitHub runs Jekyll for you every time you save a change, so you never have to touch a server.

The look of this site comes from the [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) theme. Jekyll handles turning your content into pages, and the theme decides how those pages look.

## How this repo is organized

| File or folder | What it does |
|---|---|
| `_config.yml` | Site-wide settings: your name, bio, sidebar photo, and the site URL |
| `index.md` | The home page |
| `_pages/` | The other pages: `links.md` and `contact.md` |
| `_portfolio/` | The Blog Posts page (`index.md`) and one file per post (starts with a demo post, `BP-1.md`) |
| `_data/navigation.yml` | The menu across the top of every page |
| `assets/images/` | Photos and banner images |
| `assets/docs/` | PDFs, including `CV.pdf` (your resume) |
| `_resume/cv.html` | The HTML source used to make the demo `CV.pdf`. You can edit it to make your own (see Step 5). It isn't published. |
| `assets/css/main.scss` | Site colors |
| `Gemfile` | The list of Ruby packages Jekyll needs. It's only used if you preview the site on your own computer. |

Folders whose names start with `_` are Jekyll's own folders. Jekyll reads them while building your site, but it doesn't publish them as folders on the site.

## Step 0: Get a GitHub account

If you don't have one, [sign up for GitHub](https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github).

- Choose a professional username, because it will be part of your site's URL. Something like `JaneDoe` or `JSmithNIU` works well.
- Sign up with your university email, and apply for [GitHub Education](https://docs.github.com/en/education/explore-the-benefits-of-teaching-and-learning-with-github-education/github-education-for-students/apply-to-github-education-as-a-student) to get free student benefits.

## Step 1: Make your own copy

1. At the top of this repository, click the green **Use this template** button, then **Create a new repository**.
2. Give your repository a professional name, such as `jane-doe-resume`.
3. Set it to **Public**.
4. Click **Create repository**.

From here on, make every change in **your** copy, not in this template.

## Step 2: Turn on GitHub Pages

1. In your new repository, open **Settings** and then **Pages**.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Under **Branch**, choose `main` and `/ (root)`, then click **Save**.
4. Open the **Actions** tab. A run called **pages build and deployment** will start. When it shows a green check ✅, your site is live at `https://[yourusername].github.io/[your-repo-name]/`.

The site will look broken (plain text, missing images) until you finish Step 3, because the settings still point at the template's address.

From now on, every change you commit to the `main` branch rebuilds the site automatically within a minute or two. If a run shows a red ❌, click it to read the error message. The cause is usually a typo in a `.yml` file.

## Step 3: Edit `_config.yml`

On GitHub, open `_config.yml` and click the pencil icon to edit it. It starts out with this template's own address (`71north.github.io/jekyll-resume-template`), so change these lines to match your account and repository. Keep the quotation marks around each value. In YAML files the spacing matters too, so don't change the indentation.

```yaml
title: "Jane Doe"                     # shown in the top-left of every page
name: "Jane Doe's Resume Site"
url: "https://janedoe.github.io"      # https://[yourusername].github.io
baseurl: "/jane-doe-resume"           # "/" followed by your repository name
repository: "janedoe/jane-doe-resume" # [yourusername]/[your-repo-name]
```

Then scroll down to `author:`. This controls the sidebar on the left of each page.

```yaml
author:
  name   : "Jane Doe"
  avatar : "/assets/images/jane-headshot.jpg"
  bio    : "Mechanical engineering student at Northern Illinois University."
  location: "DeKalb, Illinois"
  github : janedoe       # optional: add this line to show a GitHub link
  linkedin: jane-doe-123 # optional: the part of your LinkedIn URL after /in/
```

Click **Commit changes**.

> **`baseurl` matters.** Your site lives in a subfolder named after your repository. If `baseurl` doesn't match your repository name exactly, the styling and images on your site will break: the page shows up as plain unstyled text, and your browser's developer console lists `404` errors for files like `main.css`. If you rename your repository later, update `baseurl` to match.

## Step 4: Add your photo and write your home page

1. Open `assets/images`, then click **Add file** → **Upload files**.
2. Upload a headshot. A square image between 400 and 600 pixels wide loads quickly and looks sharp.
3. Make sure `avatar:` in `_config.yml` uses your photo's file name.
4. Open `index.md` and edit it:
   - Change the image file name in the `<img>` line to your photo:
     ```html
     <img src="{{ '/assets/images/jane-headshot.jpg' | relative_url }}" width="50%" hspace="20" align="right" alt="Jane Doe">
     ```
     The `relative_url` part adds your `baseurl` automatically, so the link works wherever your site is hosted.
   - Replace Victor's introduction with your own: who you are, what you study, and what you're interested in.
   - Delete the line saying the page is a demo.

You can delete Victor's images (`victor-avatar.jpg` and `victor-e-pride.jpg`) once nothing uses them.

## Step 5: Add your resume PDF

The **Curriculum Vitae** link in the menu opens `assets/docs/CV.pdf` in a new tab. To use your own resume:

1. Export your resume as a PDF and name it `CV.pdf`.
2. Open `assets/docs`, click **Add file** → **Upload files**, and upload it. It will replace Victor's file.

If you'd rather use a different file name, change the link in `_data/navigation.yml` to match:

```yaml
  - title: "Curriculum Vitae"
    url: /assets/docs/Jane-Doe-Resume.pdf
    target: "_blank"   # opens the PDF in a new tab
```

**No resume yet?** `_resume/cv.html` is a simple, styled resume page. Download it, change the text in any text editor, open it in your browser, and print it to PDF (in Chrome or Edge, set the destination to **Save as PDF** and turn off **Headers and footers**).

## Step 6: Write your blog posts

The **Blog Posts** page (`_portfolio/index.md`) shows each post as a section that expands when clicked.

- **To edit a post:** open `_portfolio/BP-1.md`, the demo post, and replace Victor's writing with your own. It shows the most common Markdown formatting, so it's a handy reference.
- **To add a post:** create a new file such as `_portfolio/BP-2.md`. Then add a matching block to the bottom of `_portfolio/index.md`:
  ```html
  <details markdown="1"><summary>BP-2 Your Post Title</summary>
  {% include_relative BP-2.md %}
  </details>
  ```
- **To remove a post:** delete its `<details>` block from `_portfolio/index.md`, then delete its file.

Posts are written in Markdown. If you're new to it, keep the [Markdown cheat sheet](https://www.markdownguide.org/cheat-sheet/) open while you write.

## Step 7: Update the Links and Contact pages

- `_pages/links.md`: add links to your GitHub, LinkedIn, projects, or student organizations. In Markdown, a link looks like `[Text people see](https://example.com)`.
- `_pages/contact.md`: replace the fictional email address with yours.

> **Tip:** an email address written as plain text on a website gets picked up by spam bots. You could write it as `jane [at] niu [dot] edu`, or post an image of the address instead of the text.

## Step 8: Final check

1. Visit `https://[yourusername].github.io/[your-repo-name]/`.
2. Click every menu link, and make sure the CV opens your PDF.
3. Search your repository for "Victor" to catch any leftover demo content.
4. If a change isn't showing up, wait a minute, then refresh. If it still doesn't appear, try a private/incognito window.

## Making it your own (optional)

- **Menu:** `_data/navigation.yml` controls the top menu. Each entry has a `title` and a `url`, plus an optional `target: "_blank"` to open the link in a new tab. If you delete a page, remove its menu entry too, or the menu will link to a missing page.
- **Banner images:** each page sets its own banner in the front matter (the block between `---` lines at the top of the file):
  ```yaml
  header:
    image: /assets/images/niubanner.png
  ```
  Use an image about 1280 pixels wide.
- **Colors:** in `assets/css/main.scss`, change `$primary-color` and `$link-color` to any hex color. NIU red is `#C8102E`.
- **Overall theme:** set `minimal_mistakes_skin` in `_config.yml` to another skin, such as `default`, `air`, `dark`, or `mint`. You can preview them in the [Minimal Mistakes docs](https://mmistakes.github.io/minimal-mistakes/docs/configuration/#skin).
- **Custom domain:** you can buy a domain such as `janedoe.com` and [point it at your site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).

## Previewing on your own computer (optional)

Editing on GitHub is enough for everything above. If you want to see changes instantly before publishing them, you can run the site on your own computer:

1. Install [Ruby](https://www.ruby-lang.org/en/documentation/installation/) and [Git](https://git-scm.com/downloads).
2. Clone your repository, then run these commands in its folder:
   ```bash
   bundle install
   bundle exec jekyll serve --livereload
   ```
3. Open `http://localhost:4000/[your-repo-name]/` in your browser.

Jekyll writes the finished site to a `_site/` folder. That folder is listed in `.gitignore`, so it won't be committed. GitHub builds its own copy when you push.

Pages reload automatically when you save a file. Changes to `_config.yml` are the exception: to see those, stop the server with `Ctrl+C` and start it again.

## Credits

- The theme is [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) by [Michael Rose](https://mademistakes.com), released under the MIT License. See its [documentation](https://mmistakes.github.io/minimal-mistakes/) for every setting it supports.
- The site is built with [Jekyll](https://jekyllrb.com/) and hosted on [GitHub Pages](https://pages.github.com/).
- The original site design comes from [pwills.com](https://github.com/peterewills/peterewills.github.io).
- The template was adapted for NIU students by [AdamBougher](https://github.com/adambougher) and [drklis](https://github.com/drklis/).
- Jerry ([wildjerry](https://github.com/wildjerry)) helped fix errors left over from that earlier version of the template.
