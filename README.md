# Drafting Assistance Tracker

## What Is This?

This document summarizes the status of Andrew Lee's ongoing projects focused on automating repetitive drafting tasks.

> Approximately 50% of my time is spent converting drawings from one format into another.

All work is completed on my own time. This is primarily a passion project, i just like automating things.

---

# Project 1: Hand-Drawn Butterfly Diagram → MicroStation Drawing

## Why

We spend significant time converting hand-drawn butterfly diagrams into digital drawings.

**Potential savings:** ~1 hour per manhole (MH) if the initial conversion process is automated.

## End Goal

Automatically convert hand-drawn manhole diagrams into:

1. **Bluebeam drawings** using native markups
2. **MicroStation-ready drawings** with proper layers

Additional functionality:

- Separate different circuits by color
- Automatically generate labels
- GUI-based workflow
- Fast human review loop for:
  - Circuit labels
  - Circuit paths
  - Circuit endpoints

## Status

**15% Complete**

## Completed

- Created machine-friendly MH diagram template
- Identified minimum scan requirements:
  - 24-bit RGB TIFF
  - 300 DPI
- Automated scanning via Windows Image Acquisition
- Implemented high-level color separation
- Implemented template subtraction
- Achieved <1 pixel page alignment using:
  - AprilTags
  - Checkerboard edges
- Identified high-level requirements for MicroStation export

## TODO

- Await delivery of DS-50000 large-format scanner for further development
- Laser-cut stencil to create consistent markups
- Design an internal "universal" on-page coordinate system
- Create proof of concept `.DWG` generator with:
  - Layers
  - Color handling

---

# Project 2: Ocalc → Bluebeam Stick Figure

## Purpose

Automatically convert Ocalc poles into Bluebeam native stick figures.

## Status

**60% Complete**

## Completed

- Bluebeam `.bax` format documentation
- `.bax` generator
- Relevant information extraction via `pplx_extract`
- Initial stick-figure generation
- Output template switching using isolated folders
- Additional geometry support (Termimesh and Guys)

## TODO

- Replace drawn measurement labels with Bluebeam native measurements
- Add customizable templates to generated `.bax` files
- Add text-box collision detection and prevention
- Auto-insert suggested HECO standards per pole based on:
  - Installed components
  - Number of phases
  - Span attachments and angle
  - **EXISTING vs. NEW detection**

---

# Project 3: pplx_extract

## Purpose

A general-purpose information extraction library for Ocalc `pplx` and `pplld` files.

Capabilities:

- Extracts pole shape and components
- Converts data into a typed object model
- Produces a schema-agnostic normalized tree

##
