# 🗺️ Vector Overlay in GIS

[![Deploy Jekyll with Just the Docs theme](https://github.com/def-fun7/vector_overlay_gis/actions/workflows/jekyll.yml/badge.svg)](https://github.com/def-fun7/vector_overlay_gis/actions/workflows/jekyll.yml)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Deployed-2ea44f?logo=github)](https://<your-username>.github.io/<your-repo-name>/)
[![ArcPy](https://img.shields.io/badge/ArcPy-ESRI%20ArcGIS-green)](https://pro.arcgis.com/en/pro-app/latest/arcpy/get-started/what-is-arcpy-.htm)
[![Docs: Just the Docs](https://img.shields.io/badge/Docs-Just%20the%20Docs-lightgrey)](https://just-the-docs.github.io/just-the-docs/)
[![Jekyll](https://img.shields.io/badge/Built%20with-Jekyll-blueviolet?logo=jekyll)](https://jekyllrb.com/)

**Vector Overlay in GIS** repository, contains, two main things.

- ArcGIS Pro Project
- md Docs

[argis-project](./arcgis-project/) contains **.geodatabases** both inputs and output, tool-wise that were used in this project alongside maps, with the used symbology in the project.

[docs](./docs/) consists of markdown documents written as a kind of notes and summary on the topic.

The site is hosted with **GitHub Pages** using the [Just the Docs](https://just-the-docs.github.io/just-the-docs/) theme for clean navigation and automatic in‑page Table of Contents.

---

## 📑 Contents

- **Intersect** → Features overlapping in all input layers  
- **Union** → Combines features from multiple layers  
- **Erase** → Removes features from input based on erase layer  
- **Identity** → Updates input features with identity layer attributes  
- **Update** → Replaces input polygons with update polygons  
- **Clip** → Extracts input features within clip extent  

Each tool section includes:

- Technical specifications  
- Input/Output rules based on geometry hierarchy (Point, Line, Polygon)  
- Valid input combinations  
- Example figures with visual outputs  
- ArcPy function references  

Each geodatabase includes:

- is mobile geodatabase.
- separate input and output folders.
- separate tool-wise.
- namings aren't consistent among the .geodatbase though they are rather obvious.

Then results are in png in figures, again tool-wise.

---

## 🚀 Hosted Pages

This repository is published via **GitHub Pages**.  
You can it all here:

👉 [**Live Site**](https://def-fun7.github.io/vector_overlay_gis/)

---

## 📐 Geometry Rules

Overlay tools follow the **same or lesser dimension rule**:

- **Polygon input present** → Output can be Polygon, Line, or Point  
- **Line input present** → Output can be Line or Point  
- **Point input only** → Output can only be Point  

Geometry hierarchy:  
**Polygon (2D) > Line (1D) > Point (0D)**

---

## 📆 History

This is actually a do-over of a project I did, on latex, trying to get out of writing practical notebook of GIS in my bachelors, in January, 2024. That file is provided in `docs/src/`.

---

## 🐍 ArcPy Functions

Each tool is documented with its ArcPy function signature, e.g.:

```python
arcpy.analysis.toolname(in_features, out_feature_class {**params})
```

## 📷 Figures

Example figures are included for each tool, showing input layers and resulting outputs.  
Figures are stored under:

``` bash
/assets/figures/
```

Organized by tool (e.g. `01.union/`, `02.intersect/`, `03.clip/`).

## Releases

The ArcGIS pro Project used in for this can be downloaded from the [Release Page Here](https://github.com/def-fun7/vector_overlay_gis/releases/tag/overlay-vector-18.12.31).

## 🛠️ How to Use

Clone the repository:

```bash
git clone https://def-fun7.github.io/vector_overlay_gis/
cd vector_overlay_gis
```

📄 License
This project is licensed under the MIT License. See [LICENSE](LICENSE.md) for details.
