# Education in Australia (2023)

An interactive data visualisation dashboard exploring education trends across Australia in 2023, built with Vega-Lite and Bootstrap.

## Overview

This project is a single-page web dashboard presenting six interactive visualisations derived from [Australian Bureau of Statistics (ABS)](https://www.abs.gov.au/statistics/people/education/education-and-work-australia/may-2023) data. It was developed as part of **FIT3179 – Data Visualisation** at Monash University.

## Visualisations

| Chart | Type | Key Question |
|---|---|---|
| Enrollment by State & Gender | Choropleth map | What are the current enrollment rates in educational programs? |
| Non-School Qualifications Growth | Area chart (2014–2023) | How have non-school qualifications grown over time? |
| Employment Status by Education & Gender | Double-sided bar chart | How does education level correlate with employment status? |
| High School Attainment by State | Proportional symbol map | How many Australians have at least a high school education? |
| Highest Education Level by State | Bubble chart | What are each state's most popular highest education levels? |
| Fields of Study by Gender | Grouped bar chart | What are the most popular fields of study? |

## Tech Stack

- **[Vega-Lite v5](https://vega.github.io/vega-lite/)** — declarative grammar for interactive charts (`.vg.json` specs)
- **[Vega-Embed v6](https://github.com/vega/vega-embed)** — renders Vega-Lite specs into the page
- **[Bootstrap 5.3](https://getbootstrap.com/)** — layout and responsive design
- **GeoJSON / TopoJSON** — Australian state boundaries for choropleth and symbol maps

## Project Structure

```
├── index.html                           # Main dashboard page
├── js/
│   ├── visualisations.js                # Embeds all Vega-Lite specs via vegaEmbed
│   ├── enrolled_map.vg.json             # Choropleth: enrollment by state & gender
│   ├── area_chart_non_school.vg.json    # Area chart: non-school qualifications over time
│   ├── employment_barchart.vg.json      # Bar chart: employment status by education & gender
│   ├── updated_education_map.vg.json    # Symbol map: high school attainment by state
│   ├── bubble_chart.vg.json             # Bubble chart: highest education by state
│   ├── field_of_study_barchart.vg.json  # Bar chart: fields of study by gender
│   ├── states.geojson                   # Australian state boundaries (GeoJSON)
│   └── states.topojson                  # Australian state boundaries (TopoJSON)
└── data/
    ├── Enrolled_in_study_by sex_and_state.csv
    ├── Year12_certificate_or_above_by_state.csv
    ├── field_of_study_gender.csv
    ├── highest_edu.csv
    ├── labour_force_by_gender.csv
    ├── labour_force_by_gender_new.csv
    └── time_series.csv
```

## Running Locally

The page must be served over HTTP rather than opened as a local file (to avoid CORS issues when loading data and map tiles).

Using Python's built-in server:

```bash
python3 -m http.server 8000
```

Then open [http://localhost:8000](http://localhost:8000) in your browser. Alternatively, use the VS Code Live Server extension or any static file server.

## Notes

- All CDN dependencies (Vega, Vega-Lite, vega-embed, Bootstrap) require an internet connection. For offline use, download them and update the `<script>` tags in `index.html`.
- Some visualisation specs load data from `raw.githubusercontent.com` — an internet connection is also needed for these remote data URLs.

## Data Source

All data is sourced from the **Australian Bureau of Statistics**:  
[Education and Work, Australia, May 2023](https://www.abs.gov.au/statistics/people/education/education-and-work-australia/may-2023)

---
Created by Dean Mascitti — visualisations powered by Vega-Lite.
