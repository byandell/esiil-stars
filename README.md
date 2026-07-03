# ESIIL Stars Training Notes

These notes are associated with
[ESIIL Stars](https://esiil.org/esiil-network#esiil-stars)
and the GitHub Organization
[cu-esiil-edu](https://github.com/cu-esiil-edu/stars-2026).

This repo
<https://github.com/byandell/esiil-stars>
is displayed via GitHub pages as
[byandell.github.io/esiil-stars](https://byandell.github.io/esiil-stars)
by turning on GitHub Pages in the same manner as the assignment to
[Build your Environmental Data Science portfolio](https://earthdatascience.org/pages/03-git-github/03-github-portfolio/portfolio-stars.html).

- [Keep Track of Your Work](#keep-track-of-your-work)
- [Embed Dynamic HTML in GitHub Pages](#embed-dynamic-html-in-github-pages)
- [Publish `docs/` Folder From Private Repo](#publish-docs-folder-from-private-repo)
- Additional Reading
  - [The Least You Need to Know About GitHub Pages](https://tomcam.github.io/least-github-pages/set-github-pages-master-branch.html)
  - [Document Digital Tools](https://byandell.github.io/Documentation)
    - [Publish GitHub Pages](https://byandell.github.io/Documentation/github/pages.html)
    - [Embed Objects in GitHub Pages](https://byandell.github.io/Documentation/github/embed.html)
    - [Collaborate with GitHub Organizations](https://byandell.github.io/Documentation/github/#collaborate-with-github-organizations) 

## Keep Track of Your Work

Where did I have that repo?
You can use your portfolio to keep track of your work.
This is helpful for you, and lets other people who visit your portfolio know what you have done.
This can be useful later to help build your resume, or collection of your work.
Just add links to your projects.
For instance, here is the ESIIL Stars 2026 page and textbook:

- [stars-2026](https://github.com/cu-esiil-edu/stars-2026)
- [ESIIL Stars Textbook](https://earthdatascience.org/pages/00-overviews/04a-courses/stars/)

I include profiles of ESIIL Stars students right here.
Here are migration projects in progress from OLC students (along with their profiles):

- [03-migration-MarshaJ24](https://github.com/cu-esiil-edu/03-migration-MarshaJ24) ([Marsha Janis](https://MarshaJ24.github.io))
- [03-migration-LeonAmbroseJr](https://github.com/cu-esiil-edu/03-migration-LeonAmbroseJr) ([Leon Red Kettle](https://LeonAmbroseJr.github.io))
- [03-migration-CeceCoded](https://github.com/cu-esiil-edu/03-migration-CeceCoded) ([Cecelia Two Lance](https://CeCeCoded.github.io))
- [03-migration-summer-dupree](https://github.com/cu-esiil-edu/03-migration-summer-dupree) ([Summer Dupree](https://summer-dupree.github.io))

And here are the OLC faculty:

- [Dana Gehring](https://github.com/drg799802)
- [Cami Griffith](https://github.com/camgrif)
- [Elisha *Wakinyan Zi* Yellow Thunder](https://github.com/wakinyanzi)

## Embed Dynamic HTML in GitHub Pages

The way to link a dynamic HTML file, such as a dynamic migration presentation,
is to save it in a portfolio repo that is rendered via GitHub pages,
such as using a `[homepage].github.io`.
HTML files (ending in `.html`) do not display well in GitHub,
but will display via GitHub Pages.
See
[Embed Objects in GitHub Pages](https://byandell.github.io/Documentation/github/embed.html)
for more detail.

This is with the Western Meadowlark (_Tasiyagnunpa_) from 
[cu-esiil-edu/03-migration-MarshaJ24](https://github.com/cu-esiil-edu/03-migration-MarshaJ24),
a student fork of
[cu-esiil-edu/stars-03-migration-template](https://github.com/cu-esiil-edu/stars-03-migration-template).
The dynamic HTML file is saved as
[tasiyagnunpa_migration.html](https://byandell.github.io/esiil-stars/tasiyagnunpa_migration.html).

Here we embed the dynamic HTML page in this page using

```
<iframe src="tasiyagnunpa_migration.html"
 title="Tasiyagnunpa Migration"
 width="100%" height="600px"></iframe>
```

Note the `width` and `height`, which can be tweeked.
The `title` option is useful if for some reason the page does not render.

<iframe src="tasiyagnunpa_migration.html"
 title="Tasiyagnunpa Migration"
 width="100%" height="600px"></iframe>

**Note:**
This image will not display properly in `Preview` mode or in the GitHub repo,
but it will display on the published page
<https://byandell.github.io/esiil-stars>
once the edits are committed to GitHub.

## Publish `docs/` Folder From Private Repo

This is gleaned from
[Publish GitHub Pages](https://byandell.github.io/Documentation/github/pages.html)
and adapted for the a GitHub organization like the
[OLC Integrated Data Cube](https://olc-techsupport.github.io/).
See also notes on how to
[Collaborate with GitHub Organizations](https://byandell.github.io/Documentation/github/#collaborate-with-github-organizations).

A repo for ESIIL Stars might be `private` in such an organization
but may have a `public` published set of pages
hosted from the `docs/` folder.
For instance the simple repo `private-demo` in the
[OLC Integrated Data Cube](https://olc-techsupport.github.io/)
is only visible to authorized OLC members.
However, the published page is visible to all.

- <https://github.com/olc-techsupport/private-demo> (private repo)
- <https://olc-techsupport.github.io/private-demo> (public page)

**Note:** 
Set up the GitHub Pages for the team repo to use the `docs/` folder.
Once published, things in the `docs/` folder will be `public`.


