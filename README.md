# 🎧 Spotify 2023 — Power BI Analytics & Business Intelligence

> **An end-to-end Business Intelligence project exploring Spotify 2023 music data through data preparation, analytical modeling, DAX, interactive reporting, cross-platform analysis, outlier detection, and artist concentration analysis.**

---

## 📌 Project Overview

The **Spotify 2023 Power BI Analytics Project** transforms raw music and platform-performance data into a structured Business Intelligence solution designed to support data-driven analysis of the music industry.

The project examines not only which songs achieved high streaming volumes, but also the factors associated with their performance — including **audio characteristics, playlist exposure, chart presence, cross-platform visibility, and artist concentration**.

The complete analysis was developed around six major analytical areas:

1. 🎵 Music Characteristics & Audio DNA
2. 🌐 Cross-Platform Presence
3. 📈 Playlist Exposure vs Streaming Performance
4. 🏆 Chart Presence vs Song Performance
5. 🔍 Outlier & Exceptional Song Detection
6. 👨‍🎤 Artist Concentration & Pareto Analysis

The final solution contains a **12-page Power BI report architecture** supported by a cleaned semantic model, calculated metrics, DAX measures, filters, KPIs, and business-oriented interpretations.

---

## 🎯 Project Objectives

The main objectives of this project are to:

- Clean and prepare the Spotify 2023 dataset for BI analysis.
- Build a structured Power BI semantic model.
- Analyze relationships between musical characteristics and streaming performance.
- Compare song presence across Spotify, Apple Music, Deezer, and Shazam.
- Investigate the relationship between playlist exposure and streams.
- Examine chart presence relative to streaming performance.
- Identify songs that behave differently from general market patterns.
- Measure how concentrated streaming performance is among artists.
- Transform analytical results into meaningful business insights.
- Present the findings through a professional Power BI reporting experience.

---

## 📊 Dataset Overview

The project uses the **Spotify 2023 dataset**, containing:

| Dataset Property | Value |
|---|---:|
| Song Records | **953** |
| Unique Tracks | **943** |
| Artist Entries | **645** |
| Total Streams | **489.46 Billion** |
| Median Streams | **290.53 Million** |
| Average Streams | **514.14 Million** |
| Platforms Analyzed | **Spotify, Apple Music, Deezer & Shazam** |

The dataset includes information related to:

- Track and artist details
- Release information
- Spotify streams
- Spotify playlist and chart presence
- Apple Music playlist and chart presence
- Deezer playlist and chart presence
- Shazam chart presence
- BPM
- Danceability
- Energy
- Valence
- Acousticness
- Instrumentalness
- Liveness
- Speechiness

---

## 🧹 Data Preparation & Transformation

Before visualization, the raw dataset was transformed into an analysis-ready structure.

Key preparation activities included:

- Data-type validation
- Numeric conversion of streaming values
- Cleaning playlist and chart fields
- Handling missing Shazam chart observations
- Investigating duplicate track/artist combinations
- Creating analysis-ready platform metrics
- Standardizing year and numerical fields
- Creating playlist exposure metrics
- Creating combined chart-presence metrics
- Calculating cross-platform presence
- Creating outlier classifications
- Preparing measures for artist-level analysis

### Derived Analytical Fields

**Playlist Exposure**

```text
Spotify Playlists + Apple Playlists + Deezer Playlists
```

**Chart Presence**

```text
Spotify Charts + Apple Charts + Deezer Charts + Shazam Charts
```

**Platform Count**

Measures whether a track has observed presence across:

```text
Spotify + Apple Music + Deezer + Shazam
```

This provides a simple indicator of a song's **cross-platform breadth**.

---

# 📑 Power BI Report Architecture

The project is organized into **12 analytical pages**.

## 01 — Executive Overview

Provides a management-level summary of the dataset and major performance indicators.

Key KPIs include:

- Total Streams
- Song Records
- Unique Tracks
- Artist Entries
- Median Streams

The page provides an immediate understanding of the scale and structure of the analyzed catalog.

---

## 02 — Music DNA | Audio Profile

Analyzes the overall musical characteristics of tracks.

Major indicators:

| Audio Feature | Average |
|---|---:|
| BPM | **122.54** |
| Danceability | **66.97%** |
| Energy | **64.28%** |
| Valence | **51.43%** |
| Acousticness | **27.06%** |
| Instrumentalness | **1.58%** |
| Liveness | **18.21%** |
| Speechiness | **10.13%** |

This page helps describe the overall **audio profile of the catalog**.

---

## 03 — Music DNA | Relationships

Investigates whether individual musical characteristics have strong linear relationships with streaming performance.

Observed Pearson correlations with streams were relatively weak:

| Feature | Correlation with Streams |
|---|---:|
| BPM | -0.002 |
| Acousticness | -0.004 |
| Energy | -0.026 |
| Valence | -0.041 |
| Instrumentalness | -0.045 |
| Liveness | -0.048 |
| Danceability | -0.105 |
| Speechiness | -0.112 |

### 💡 Insight

No individual audio characteristic in this dataset shows a strong linear relationship with total streams.

This suggests that streaming performance should not be interpreted as being explained by a single musical characteristic.

---

## 04 — Cross-Platform Intelligence

Examines how widely tracks appear across the available music platforms.

### Platform Breadth

| Number of Platforms | Songs |
|---|---:|
| 4 Platforms | **549** |
| 3 Platforms | **376** |
| 2 Platforms | **24** |
| 1 Platform | **4** |

### 💡 Insight

Most songs in the dataset have presence across multiple platforms, with **549 tracks showing four-platform presence**.

Platform Count is treated as a **breadth indicator**, not as a direct performance score, because playlist and chart metrics use different scales across platforms.

---

## 05 — Playlist Exposure vs Streaming Performance

One of the project's major analyses investigates whether songs with greater playlist exposure also tend to have higher accumulated streams.

### Key Result

```text
Playlist Exposure ↔ Streams
Pearson Correlation ≈ 0.783
```

This represents a **strong positive association** within the available dataset.

### 💡 Interpretation

Songs with greater playlist exposure tend to have higher accumulated streaming totals.

However:

> **Correlation does not establish causation.**

The analysis therefore describes an association rather than claiming that playlist placement directly caused the observed streaming performance.

---

## 06 — Playlist Efficiency & Exceptions

Not every successful song follows the general playlist-exposure pattern.

This page identifies tracks with:

- High streams despite comparatively lower playlist exposure
- High playlist exposure but comparatively lower streams
- High performance on both dimensions
- Typical performance patterns

Examples of high-stream / relatively-low-exposure tracks include:

- **When I Was Your Man — Bruno Mars**
- **Die For You — The Weeknd**
- **Locked Out Of Heaven — Bruno Mars**
- **Enemy — Imagine Dragons**
- **Butter — BTS**

These exceptions are useful because they identify tracks whose performance differs from the broader relationship observed in the dataset.

---

## 07 — Chart Performance Intelligence

This analysis compares chart presence with streaming totals.

### Observed Relationships

```text
Playlist Exposure ↔ Streams ≈ 0.783
Chart Presence ↔ Streams ≈ 0.107
```

### 💡 Insight

Within this dataset, accumulated streams have a much stronger linear association with playlist exposure than with the available combined chart-presence measure.

This does **not** imply that chart performance is unimportant. The available chart variables measure a different aspect of song performance and use different platform-specific scales.

---

## 08 — Outlier Detection

A quadrant-based analytical framework was created using streaming and playlist-exposure thresholds.

Songs are classified into:

```text
🟢 High Performer
🟡 High Streams / Lower Exposure
🔵 High Exposure / Lower Streams
⚪ Typical
```

The analysis uses upper-quartile thresholds of approximately:

```text
Streams Q3            = 673.87M
Playlist Exposure Q3  = 5,992
```

This allows exceptional songs to be identified systematically instead of relying only on simple rankings.

---

## 09 — Exceptional Song Deep Dive

The song-level analysis brings together:

- Streams
- Playlist exposure
- Chart presence
- Platform breadth
- BPM
- Danceability
- Energy
- Valence
- Other audio characteristics

The purpose is to investigate **why an individual track appears unusual relative to broader dataset patterns**.

---

## 10 — Artist Concentration | Pareto Analysis

The project also examines whether streaming performance follows a strict **80/20 pattern**.

### Result

```text
Total Artist Entries       = 645
Artists Required for 80%   = 217
Share of Artists           ≈ 33.6%
```

### 💡 Insight

Approximately **33.6% of artist-name combinations account for 80% of the observed streams**.

Therefore, this dataset shows meaningful concentration, but it does **not** follow a strict 80/20 distribution.

---

## 11 — Artist Portfolio Analysis

Artist-level analysis compares:

- Number of tracks
- Total streams
- Average streams per track
- Streaming contribution
- Artist ranking

Some of the largest artist-level stream totals in the dataset include:

| Artist | Approx. Streams |
|---|---:|
| The Weeknd | **14.19B** |
| Taylor Swift | **14.05B** |
| Ed Sheeran | **13.91B** |
| Harry Styles | **11.61B** |
| Bad Bunny | **10.00B** |

The analysis distinguishes between artists benefiting from a **larger catalog presence** and artists generating particularly strong performance per track.

---

## 12 — Methodology & Quality Assurance

The final section documents:

- Data preparation
- Analytical assumptions
- Metric definitions
- Data-quality considerations
- Power BI model structure
- DAX measures
- Filters and slicers
- Interpretation limitations

This provides transparency around how the analysis was performed.

---

# 🏆 Top Streaming Tracks

Some of the highest-streamed tracks in the dataset are:

| Rank | Track | Artist | Streams |
|---:|---|---|---:|
| 1 | Blinding Lights | The Weeknd | **3.70B** |
| 2 | Shape of You | Ed Sheeran | **3.56B** |
| 3 | Someone You Loved | Lewis Capaldi | **2.89B** |
| 4 | Dance Monkey | Tones and I | **2.86B** |
| 5 | Sunflower | Post Malone, Swae Lee | **2.81B** |

---

# 📐 DAX Measures

The semantic model contains analytical measures such as:

```DAX
Total Streams =
SUM(Spotify[streams_clean])
```

```DAX
Unique Tracks =
DISTINCTCOUNT(Spotify[track_name])
```

```DAX
Unique Artists =
DISTINCTCOUNT(Spotify[artist(s)_name])
```

```DAX
Average Streams =
AVERAGE(Spotify[streams_clean])
```

```DAX
Median Streams =
MEDIAN(Spotify[streams_clean])
```

```DAX
Total Playlist Exposure =
SUM(Spotify[playlist_exposure])
```

```DAX
Total Chart Presence =
SUM(Spotify[chart_presence])
```

```DAX
Artist Rank =
RANKX(
    ALLSELECTED(Spotify[artist(s)_name]),
    [Total Streams],
    ,
    DESC,
    DENSE
)
```

```DAX
Stream Contribution % =
DIVIDE(
    [Total Streams],
    CALCULATE(
        [Total Streams],
        ALLSELECTED(Spotify)
    )
)
```

---

# 🧠 Major Business Insights

The analysis produced several important findings:

**1. Playlist exposure has the strongest observed relationship with streaming scale.**  
The correlation between playlist exposure and streams is approximately **0.783**, indicating a strong positive association.

**2. Chart presence shows a much weaker linear relationship with accumulated streams.**  
The corresponding correlation is approximately **0.107**.

**3. Individual audio characteristics do not strongly explain streaming totals.**  
None of the analyzed audio features demonstrate a strong linear correlation with streams.

**4. Cross-platform presence is common.**  
549 tracks have observed presence across all four analyzed platforms.

**5. Exceptional tracks exist outside the dominant exposure pattern.**  
Several songs achieve very high streaming totals despite comparatively lower playlist exposure.

**6. Artist performance is concentrated, but not according to a strict 80/20 rule.**  
Approximately 33.6% of artist-name combinations are required to account for 80% of streams.

---

# 🛠️ Technology Stack

![Power BI](https://img.shields.io/badge/Power%20BI-Business%20Intelligence-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Analytics-blue?style=for-the-badge)
![Power Query](https://img.shields.io/badge/Power%20Query-ETL-green?style=for-the-badge)
![GitHub](https://img.shields.io/badge/GitHub-Version%20Control-black?style=for-the-badge&logo=github)
![CSV](https://img.shields.io/badge/CSV-Data-orange?style=for-the-badge)

### Core Tools

- **Microsoft Power BI Desktop**
- **Power Query**
- **DAX**
- **PBIP / PBIR**
- **TMDL Semantic Model**
- **Git & GitHub**

---

# 📂 Repository Structure

```text
Spotify-2023-Power-BI-Analysis/
│
├── BI Practical MST.pbip
│
├── Spotify_2023_Analytics.Report/
│   ├── definition/
│   └── StaticResources/
│
├── Spotify_2023_Analytics.SemanticModel/
│   └── definition/
│
├── data/
│   └── spotify-2023-cleaned.csv
│
├── Spotify_2023_BI_Consulting_Report.pdf
│
├── README.md
├── .gitignore
└── README - OPEN BI PRACTICAL MST.txt
```

---

# 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/Spotify-2023-Power-BI-Analysis.git
```

### 2. Open the project folder

```bash
cd Spotify-2023-Power-BI-Analysis
```

### 3. Launch Power BI

Open:

```text
BI Practical MST.pbip
```

using **Microsoft Power BI Desktop**.

The `.Report` and `.SemanticModel` directories must remain alongside the `.pbip` file.

---

# ⚠️ Analytical Limitations

The results should be interpreted within the scope of the supplied dataset.

In particular:

- Correlation does not prove causation.
- Streams represent accumulated performance rather than a historical streaming time series.
- Release date should not be interpreted as stream transaction date.
- Platform playlist/chart variables have different scales.
- Missing Shazam observations require careful treatment.
- Artist names containing multiple collaborators are treated according to the supplied artist-name field.
- The dataset does not contain revenue, cost, listener demographics, geographic attributes, or individual customer information.
- No forecasting or predictive modeling is used.

These limitations are intentionally documented to avoid overstating the conclusions.

---

# 💼 Business Value

This project demonstrates how raw entertainment-industry data can be transformed into a structured BI solution capable of supporting questions such as:

- Which songs dominate streaming performance?
- How strongly is playlist exposure associated with streams?
- Which tracks outperform their observed exposure?
- How broad is cross-platform presence?
- Do chart variables show the same relationship with streams as playlist exposure?
- Which artists account for the largest share of streaming activity?
- Is streaming performance highly concentrated among a small number of artists?
- Do musical characteristics distinguish highly streamed songs?

The project demonstrates the complete analytical workflow from **raw data → transformation → modeling → DAX → visualization → interpretation → business insight**.

---

# 👨‍💻 Author

## Shibaji Biswas

**Artificial Intelligence & Machine Learning**

Focused on:

`Artificial Intelligence` • `Machine Learning` • `Data Analytics` • `Business Intelligence` • `Power BI` • `Data Visualization`

---

## ⭐ Project Summary

> This project demonstrates an end-to-end Business Intelligence approach to Spotify 2023 data by combining data preparation, semantic modeling, DAX, interactive reporting, statistical association analysis, outlier detection, cross-platform intelligence, and Pareto analysis to transform raw music data into evidence-based business insights.

---

### ⭐ If you find this project useful, consider starring the repository.
