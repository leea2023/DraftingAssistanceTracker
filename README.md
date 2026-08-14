# Drafting Assistance Tracker

## What Is This?

This summarizes the status of Andrew Lee's ongoing projects focused on automating repetitive drafting tasks.

All work is completed on my own time. Primarily a passion project; the amount of time i spend on this is much larger than the time I save

---

# Project 1: pplx_extract

## Purpose

A general-purpose information extraction library for Ocalc `pplx` and `pplld` files.

Capabilities:

- Extracts pole shape and components
- Produces a schema-agnostic normalized tree, converted into a typed object model


## Status

**Complete**
https://github.com/leea2023/pplx_extract
Feel free to use and suggest any improvements!

# Project 2: Hand-Drawn Butterfly Diagram → MicroStation Drawing

## Why

We spend significant time converting hand drawn butterfly diagrams into digital drawings.

**Potential savings:** 1 hour per manhole if the initial conversion process is automated.

## End Goal

Automatically convert hand-drawn manhole diagrams into:

1. **Bluebeam drawings** using native markups
2. **MicroStation-ready drawings** with proper layers

Additional functionality:

- Separate different circuits by color
- Automatically generate labels (using OCR or locally run vision LLM? not sure yet)
- GUI-based workflow with human review loop

## Status

**15%**

## Completed

- Created new, machine-friendly MH diagram template
- Identified minimum scan requirements:
  - 24-bit RGB TIFF
  - 300 DPI
- Confirmed Windows Image Acquisition works
- Proof of concept high-level color separation
- Proof of concept template subtraction
- Achieved <1 pixel page alignment using:
  - AprilTags
  - Checkerboard edges
- Identified high-level requirements for MicroStation export requirements

## TODO

- Await delivery of DS-50000 large-format scanner for further development
- Laser-cut stencil to create consistent markups
- Design an internal "universal" on-page coordinate system
- Create proof of concept `.DWG` generator with:
  - Layers
  - Color handling

---

# Project 3: Ocalc → Bluebeam Stick Figure

## Purpose

Automatically convert Ocalc poles into Bluebeam native stick figures.

## Status

**60%**

## Completed

- Bluebeam `.bax` format documentation
- `.bax` generator
- Relevant information extraction via `pplx_extract`
- Initial stick-figure generation
- Output template switching using isolated folders
- Additional geometry support (Termimesh and Guys)

## TODO

- Replace drawn measurement labels with Bluebeam native measurements
- Add the option for user imported "templates" to generated `.bax` files
- Add text-box collision detection and prevention
- Detect and suggest HECO standards per pole based on:
  - Components
  - Number of phases
  - Span attachments and angle
  - **EXISTING vs. NEW detection**

---


##
