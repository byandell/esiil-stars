# ESIIL Stars Training Notes

This repo
[esiil-stars](https://github.com/byandell/esiil-stars)
is displayed via GitHub pages as
[byandell.github.io/esiil-stars](https://byandell.github.io/esiil-stars)
by turning on GitHub Pages in the same manner as the assignment to
[Build your Environmental Data Science portfolio](https://earthdatascience.org/pages/03-git-github/03-github-portfolio/portfolio-stars.html).

- [Keeping Track of Your Work](#keeping-track-of-your-work)
- [Displaying HTML Pages](#displaying-html-pages)
  - [Linking the HTML Page](#linking-the-html-page)
  - [Embedding Dynamic HTML in Published GitHub Pages](#embedding-dynamic-html-in-published-github-pages)
- [Raw vs Rendered GitHub Pages](#raw-vs-rendered-github-pages)
- [Publishing From a Repo with GitHub Pages](#publishing-from-a-repo-with-github-pages)
- [Documentation for Digital Tools](https://byandell.github.io/Documentation)
  - [Collaborating with GitHub Organizations](https://byandell.github.io/Documentation/github/#collaborating-with-github-organizations) 

## Keeping Track of Your Work

Where did I have that repo?
You can use your portfolio to keep track of your work.
This is helpful for you, and lets other people who visit your portfolio know what you have done.
This can be useful later to help build your resume, or collection of your work.
Just add links to your projects.
For instance, here is the ESIIL Stars 2026 page and textbook:

- [stars-2026](https://github.com/cu-esiil-edu/stars-2026)
- [ESIIL Stars Textbook](https://earthdatascience.org/pages/00-overviews/04a-courses/stars/)

I can include work of ESIIL Stars students right here.
Here are some migration projects in progress from OLC:

- [03-migration-summer-dupree](https://github.com/cu-esiil-edu/03-migration-summer-dupree)
- [03-migration-MarshaJ24](https://github.com/cu-esiil-edu/03-migration-MarshaJ24)
- [03-migration-LeonAmbroseJr](https://github.com/cu-esiil-edu/03-migration-LeonAmbroseJr)

## Displaying HTML Pages

The way to link an HTML file, such as a dynamic migration presentation,
is to save it in a portfolio repo that is rendered via GitHub pages,
such as using a `[homepage].github.io`.
HTML files (ending in `.html`) do not display well in GitHub,
but will display via GitHub Pages.

### Linking the HTML Page

Here is the Western Meadowlark (_Tasiyagnunpa_) from 
[cu-esiil-edu/03-migration-MarshaJ24](https://github.com/cu-esiil-edu/03-migration-MarshaJ24)
first trying to display the remote file,
then using GitHub Pages rendering the locally stored in this repo.

- [Remote file tasiyagnunpa_migration.html](https://github.com/cu-esiil-edu/03-migration-MarshaJ24/blob/main/notebooks/tasiyagnunpa_migration.html)
- [Local copy of tasiyagnunpa_migration.html](tasiyagnunpa_migration.html)

Here are 2 versions of the same HTML file with explicit link
the last two display as they are located in github pages.

- [portfolio page](https://byandell.github.io/esiil-stars/tasiyagnunpa_migration.html) (renders)
- [portfolio repo](https://github.com/byandell/esiil-stars/blob/main/tasiyagnunpa_migration.html) (does not render)

### Embedding Dynamic HTML in Published GitHub Pages

Here we embed the dynamic HTML page in this page:

<embed type="text/html" src="tasiyagnunpa_migration.html" width="1200" height="600">

**Warning:**
This image will not dispay in `Preview` mode or in the GitHub repo,
but it will display on the published page
<https://byandell.github.io/esiil-stars/>
once the edits are committed to GitHub.

Here is the code used in this `README.md` document.
It is actually written in HTML that can be included in a markdown document.
Note the `width` and `height`, which can be tweeked.

```
<embed type="text/html" src="tasiyagnunpa_migration.html" width="1200" height="600">
```

## Raw vs Rendered GitHub Pages

It is helpful to notice how the
[`esiil-stars` published portfolio](https://byandell.github.io/esiil-stars)
and the
[README.md in GitHub](https://github.com/byandell/esiil-stars/blob/main/README.md)
versions of this page differ.

Here are 3 different versions of this `README.md` page of this repo. 
Hover over the link to reveal where it is going.

- [byandell.github.io/esiil-stars](https://byandell.github.io/esiil-stars) (published portfolio via GitHub Pages)
- [byandell/esiil-stars/README.md](https://github.com/byandell/esiil-stars/blob/main/README.md) (rendered markdown via GitHub)
- [byandell.github.io/esiil-stars/README.md](https://byandell.github.io/esiil-stars/README.md) (raw markdown via GitHub Pages)

## Publishing From a Repo with GitHub Pages

This set of documents is published using
[GitHub Pages](https://byandell.github.io/Documentation/github/#github-pages)
from the repo
<https://github.com/byandell/esiil-stars>.
For a GitHub organization like the
[OLC Integrated Data Cube](https://olc-techsupport.github.io/),
a repo for ESIIL Stars might be `private`
but may have a `public` published set of pages
hosted from the `docs/` folder.
For instance (with fake repo name `olc_stars`):

- `https://github.com/olc-techsupport/olc_stars` (private repo)
- `https://olc-techsupport.github.io/olc_stars` (public pages)

In that case, it is important to set up the GitHub Pages for the team repo to be in the `docs/` folder.
Note that once published, things in the `docs/` folder will be `public`.
Here is a site with fairly good instructions to set this up:

- [The Least You Need to Know About GitHub Pages](https://tomcam.github.io/least-github-pages/set-github-pages-master-branch.html)

