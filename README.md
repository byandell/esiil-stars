# ESIIL Stars Training Notes

These notes are associated with ESIIL Stars 2026 Cohort:

- [ESIIL Stars](https://esiil.org/esiil-stars)
- [cu-esiil-edu](https://github.com/cu-esiil-edu) GitHub Organization
  - [cu-esiil-edu/stars-2026](https://github.com/cu-esiil-edu/stars-2026)

This repo
<https://github.com/byandell/esiil-stars>
is published via GitHub pages as
[byandell.github.io/esiil-stars](https://byandell.github.io/esiil-stars)
by turning on GitHub Pages in the same manner as the assignment to
[Build your Environmental Data Science portfolio](https://earthdatascience.org/pages/03-git-github/03-github-portfolio/portfolio-stars.html).

## Table of Contents

- [Keep Track of Your Work](#keep-track-of-your-work)
- [Embed Dynamic HTML in GitHub Pages](#embed-dynamic-html-in-github-pages)
- [Sliders on Dynamic HTML](#sliders-on-dynamic-html)
- [Scatter Plots to Relate Measurements](#scatter-plots-to-relate-measurements)
- [Publish with GitHub Pages](#publish-with-github-pages)
  - [Published ESIIL Stars Projects](#published-esiil-stars-projects) 
  - [Publish `docs/` Folder From Private Repo](#publish-docs-folder-from-private-repo)
    - [Prototype Publishing with `cu-esiil-edu` Org](#prototype-publishing-with-cu-esiil-edu-org)
    - [Prototype Publishing with OLC Org](#prototype-publishing-with-olc-org)
- Additional Reading
  - [ESIIL Stars (EDS Learning Portal)](https://earthdatascience.org/pages/00-overviews/04a-courses/stars/)
  - [The Least You Need to Know About GitHub Pages](https://tomcam.github.io/least-github-pages/set-github-pages-master-branch.html)
  - [Document Digital Tools](https://byandell.github.io/Documentation)
    - [Publish GitHub Pages](https://byandell.github.io/Documentation/github/pages.html)
    - [Embed Objects in GitHub Pages](https://byandell.github.io/Documentation/github/embed.html)
    - [Collaborate with GitHub Organizations](https://byandell.github.io/Documentation/github/#collaborate-with-github-organizations)
    - [Interactive and Dynamic Plots](https://byandell.github.io/Documentation/python/interactive.html)
    - [Data Sciences](https://byandell.github.io/Documentation/datasci/)
   
*[byandell/esiil-stars](https://github.com/byandell/esiil-stars)*

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

## Sliders on Dynamic HTML

With data over time, it is nice to have sliders.
Including sliders depends on the type of dynamic plot package.
For more information, see
[Interactive and Dynamic Plots](https://byandell.github.io/Documentation/python/interactive.html)

### HVPLOT

One example used above is a slider on an HVPLOT object.
For this, see
[Marsha's migration-mj notebook](https://github.com/cu-esiil-edu/03-migration-MarshaJ24/blob/main/notebooks/migration-mj.ipynb).
Key code blocks:

```python
# Join the occurrences with the plotting GeoDataFrame
occurrence_gdf = ecoregions_gdf.merge(
    occurrence_df.reset_index(), 
    on='eco_code')

# Get the plot bounds so they don't change with the slider
xmin, ymin, xmax, ymax = occurrence_gdf.total_bounds

# Define the slider widget
slider = pn.widgets.DiscreteSlider(
    name='month',
    options={calendar.month_name[i]: i for i in range(1, 13)}
)

# Plot occurrence by ecoregion and month
migration_plot = (
    occurrence_gdf
    .hvplot(
        c='norm_occurrences',
        groupby='month',
        # Use background tiles
        geo=True, crs=ccrs.Mercator(), tiles='CartoLight',
        title=f"{species_name} migration",
        xlim=(xmin, xmax), ylim=(ymin, ymax),
        frame_width=500,
        colorbar=False,
        widgets={'month': slider},
        widget_location='bottom'
    )
)
```

```python
migration_plot.save(f'{plot_filename}.html', embed=True)
```

### GEEPLOT

Another version is to use
[Google Earth Engine Map (geemap)](https://geemap.org/).
For instance, see the example
[72 time slider gui](https://geemap.org/notebooks/72_time_slider_gui/)
Here is the code:

```python
import ee
import geemap
# geemap.update_package()
Map = geemap.Map(center=[37.75, -122.45], zoom=12)

S2 = (
    ee.ImageCollection("COPERNICUS/S2_SR")
    .filterBounds(ee.Geometry.Point([-122.45, 37.75]))
    .filterMetadata("CLOUDY_PIXEL_PERCENTAGE", "less_than", 10)
)

vis_params = {"min": 0, "max": 4000, "bands": ["B8", "B4", "B3"]}

Map.addLayer(S2, {}, "Sentinel-2", False)
Map.add_time_slider(S2, vis_params)
Map
```

## Scatter Plots to Relate Measurements

A scatter plot is an XY-plot of two measurements, ideally augmented with color and trend lines and maybe even facets.
Data scientists do this all the time in `R` with the
[ggplot2](https://ggplot2.tidyverse.org/) package,
which has a Python version as
[plotnine](https://plotnine.readthedocs.io/).

A question came up of how to relate rain and drought (or any other measures over time and space).
I figured out how to create the plot I suggested from cumulative rain and drought.
I used an example of two counties in SD, which are homes to Oglala Lakota (Pine Ridge in Oglala Lakota County)
and Sicangu (Rosebud in Todd County).
Here are links to the published reports and the GitHub repo.
The code uses `plotnine` in python.

- <https://byandell.github.io/rainDrought/> (published report)
- <https://github.com/byandell/rainDrought> (GitHub repo)

I think it is much better to show data explicitly (and do it early in a report) rather than talk about the concept.
I also do not think correlation works well when considering processes over time and space,
where there is substantial auto-correlation build in and variability due to the scale of measures.
Cumulative measures are much better behaved for a variety of reasons.

I have another example using `plotnine` in the section
[Scatter Plots with GGplot](https://byandell-envsys.github.io/landmapyr/climate.html#scatter-plots-with-ggplot)
of an EDA report
[Habitat suitability under climate change](https://byandell-envsys.github.io/landmapyr/climate.html).

Additional information about data science approaches can be found in
[Data Sciences](https://byandell.github.io/Documentation/datasci/).

## Publish with GitHub Pages

This is gleaned from
[Publish GitHub Pages](https://byandell.github.io/Documentation/github/pages.html)
and adapted for the a GitHub organization like the
[OLC Integrated Data Cube](https://olc-techsupport.github.io/).
See also notes on how to
[Collaborate with GitHub Organizations](https://byandell.github.io/Documentation/github/#collaborate-with-github-organizations).

### Published ESIIL Stars Projects

This is a list of some ESIIL Stars projects published with GitHub Pages.

- [Spatiotemporal Trends in Colorado’s Hydrologic Systems](https://lakevs14.github.io/ESIIL/) |
[GitHub Repo](https://github.com/Lakevs14/ESIIL) ([MSU Denver](https://www.msudenver.edu/))

### Publish `docs/` Folder From Private Repo

A repo for ESIIL Stars might be `private` in such an organization
but may have a `public` published set of pages
hosted from the `docs/` folder.

**Note:** 
To set up the `GitHub Pages` for a `GitHub Organization` repo
to use the `docs/` folder, follow
[The Least You Need to Know About GitHub Pages](https://tomcam.github.io/least-github-pages/set-github-pages-master-branch.html).
Once published, things in the `docs/` folder will be `public`.
If the repo is `private`, it will remain `private`.

#### Prototype Publishing with `cu-esiil-edu` Org 

The simple repo `private-repo` in the
[ESIIL Education](https://cu-esiil-edu.github.io/)
GitHub Organization
is only visible to authorized members,
which are typically ESIIL faculty and staff. 
However, the published page is visible to all.

- <https://github.com/cu-esiil-edu/private-repo> (private repo)
- <https://cu-esiil-edu.github.io/private-repo> (public profile)

For contrast, consider the `public-repo` in the same organization,
for with both the GitHub repo and the GitHub Pages profile are visible:

- <https://github.com/cu-esiil-edu/public-repo> (public repo)
- <https://cu-esiil-edu.github.io/public-repo> (public profile)

#### Prototype Publishing with OLC Org 

Here is another prototype using one of the ESIIL Stars teams.
(Note how `cu-esiil-edu` is replaced by `olc-techsupport` below
and in the repos.)
The simple repo `private-repo` in the
Oglala Lakota College GitHub Organization
[OLC Integrated Data Cube](https://olc-techsupport.github.io/)
is only visible to authorized OLC members.
However, the published page is visible to all.

- <https://github.com/olc-techsupport/private-repo> (private repo)
- <https://olc-techsupport.github.io/private-repo> (public profile)

For contrast, consider the `public-repo` in the same organization,
for with both the GitHub repo and the GitHub Pages profile are visible:

- <https://github.com/olc-techsupport/public-repo> (public repo)
- <https://olc-techsupport.github.io/public-repo> (public profile)


