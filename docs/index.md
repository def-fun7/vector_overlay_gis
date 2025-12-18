---
layout: default
title: Home
nav_order: 1
description: "Welcome to the Vector Overlay technical documentation."
has_toc: true
---

## 🗺️ Vector Overlay Concepts

This documentation introduces the fundamental **overlay operations in GIS**. Overlay analysis is one of the most powerful techniques in spatial analysis, allowing you to combine multiple datasets to reveal relationships, patterns, and new insights.

---

## 📖 Introduction

In GIS, **Overlay** is defined as *“the process of taking two or more different thematic maps of the same area and placing them on top of one another to form a new map.”*  
It is a GIS operation that superimposes multiple datasets (representing different themes) together for the purpose of identifying relationships between them. Overlay not only combines the spatial features of the datasets but also merges their attribute information. In simple terms, it creates a composite map by combining the geometry and attributes of the input datasets.  

Tools are available in most GIS software for overlaying both **vector** and **raster** data, however, we are only gonna talk about vector overlay at the moment.

---

## 🧩 Feature Types and Overlay

Overlay methods can be performed on two or more layers of the same or different geometry, depending on the method. As **Point, Line, and Polygon** are the three basic feature types in vector data, grouping them by two gives nine different combinations (allowing repetition). Based on these, overlay operations can be classified into:

- point‑on‑point overlay  
- point‑on‑line overlay  
- point‑in‑polygon overlay  
- line‑on‑point overlay  
- line‑on‑line overlay  
- line‑in‑polygon overlay  
- polygon‑on‑point overlay  
- polygon‑on‑line overlay  
- polygon‑in‑polygon overlay  

Here, the first is the input layer and the latter is the overlay layer. However, most overlay methods don’t permit all of them. They are often reduced to the three with polygon as overlay layers (i.e. 3, 6, 9).

---

## ⚙️ Overlay Methods

Overlay operations are based on logical connectors like **AND, OR, NOT** and their combinations. In accordance with these, there are three major methods commonly used in overlaying. GIS software provides tools that follow these methods and apply them to the given inputs. In the ArcGIS environment, the three main operations and their tools are:

- **Union** → Union tool  
- **Intersection** → Intersect tool  
- **Subtract** → Erase tool  

> **Note:** Different GIS software may implement these operations slightly differently or use different tool names. The implementation described here is specific to ArcGIS, but the core concepts are general.

Other overlay operations include **Symmetrical Difference**, **Update**, **Clip**, and **Identity**. These can be performed as combinations of the main three in different configurations. The major ones are described later in this documentation.

---

## 📐 The Same or Lesser Dimension Rule

In vector GIS overlay, the **output geometry can never be of higher dimension than the inputs**.  
This means:

- **Point (0‑D)**, **Line (1‑D)**, and **Polygon (2‑D)** are the three basic feature types.
- When overlaying two layers, the resulting geometry is constrained to the **lowest dimension among the inputs**.

### 🔎 Examples

- **Point ∩ Polygon** → Output is **points** (points inside polygons).  
- **Line ∩ Polygon** → Output is **lines** (line segments inside polygons).  
- **Polygon ∩ Polygon** → Output is **polygons** (classic overlay operations like Union or Intersect).  
- **Line ∩ Line** → Output is **lines** (overlapping segments) or **points** (intersection nodes).  
- **Point ∩ Line** → Output is **points** (points lying on lines).

### ✅ Implications

- All nine input/overlay combinations (Point/Line/Polygon × Point/Line/Polygon) are valid in theory.  
- In practice, GIS software often emphasizes **polygon overlays** (point‑in‑polygon, line‑in‑polygon, polygon‑on‑polygon) because they are the most common and most useful.  
- Specialized cases like point‑on‑point or line‑on‑line overlays exist, but are less frequently used.

### 📊 Summary Table

| Input Layer | Overlay Layer | Output Dimension | Typical Use Case |
|-------------|---------------|------------------|------------------|
| Point       | Point         | Point            | Coinciding points |
| Point       | Line          | Point            | Points lying on lines |
| Point       | Polygon       | Point            | Points inside polygons |
| Line        | Point         | Point            | Intersection points |
| Line        | Line          | Line/Point       | Overlapping segments or intersection nodes |
| Line        | Polygon       | Line             | Line segments inside polygons |
| Polygon     | Point         | Point            | Points inside polygons |
| Polygon     | Line          | Line             | Line segments inside polygons |
| Polygon     | Polygon       | Polygon          | Union, Intersect, Erase, etc. |

---

👉 This rule ensures overlay outputs are logically consistent and prevents nonsensical results (e.g., points producing polygons). It’s a foundational principle for understanding how GIS overlay tools behave.

---

## 🔗 Core Overlay Operations

1. [Union](./md/01.Union.md)  
2. [Intersect](./md/02.Intersect.md)  
3. [Erase](./md/03.erase.md)  
4. [Identity](./md/04.identity.md)  
5. [Update](./md/05.update.md)

---

## ⚖️ Symmetry & Difference

1. [Symmetrical Difference](./md/06.sym_diff.md)

---

## ✂️ Extraction & Counting

1. [Clip](./md/07.clip.md)  
2. [Count Overlapping Features](./md/08.overlap_fc.md)

---

## 🌍 Why Overlay Matters

Overlay analysis is central to answering spatial questions such as:

- *Where do environmental risks overlap with population centers?*  
- *Which parcels fall within both flood zones and zoning restrictions?*  
- *How do different land‑use layers interact to shape planning decisions?*  

By mastering these tools, you’ll be able to perform advanced spatial analysis and make data‑driven decisions with confidence.
