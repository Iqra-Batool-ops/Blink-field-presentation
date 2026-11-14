# Blink Field — Blink the SPHEREx Sky

**NASA Space Apps Challenge 2026 · SPHEREx challenge**

Blink Field is a public-facing sky-exploration concept designed to help people inspect how a selected region of the sky changes across observation epochs. Users provide Right Ascension (RA) and Declination (Dec), then view a time sequence of images to look for moving objects and changes in brightness.

> **Project-name note:** The presentation deck calls the project **Blink Field**, while the supplied labelled interface screenshots show the application name **SphereBlink**. This repository keeps both original files unchanged. Choose one final public-facing name and make it consistent before submission.

## The challenge

SPHEREx surveys the entire sky in 102 near-infrared bands, revisiting the sky over time. Comparing observations can help reveal objects that move or vary in brightness, including asteroids, comets, stars and brown dwarfs.

The challenge asks teams to build an accessible web tool that:
- accepts sky coordinates (RA and Dec);
- displays a sequence of images for the selected sky region;
- lets users play, pause and step through observation frames;
- makes changes between epochs easier to inspect.

## Project materials

| Material | Description |
|---|---|
| [Presentation slides (PDF)](presentation/Blink Field_Presentation.pdf) | Easy-to-preview 10-slide project presentation |
| [Editable PowerPoint](presentation/Blink Field_Presentation.pptx) | Original presentation deck |
| [Labelled interface screenshots (PDF)](reference/SphereBlink_labelled_screens.pdf) | Two annotated pages explaining the application interface |
| [Top-of-page screenshot](assets/screenshots/sphereblink-top-labelled.png) | Preview of the upper interface |
| [Lower-page screenshot](assets/screenshots/sphereblink-lower-labelled.png) | Preview of the lower interface |

## Proposed experience

1. A user enters RA and Dec or selects one of the challenge targets.
2. The tool loads the available observation frames for that sky position.
3. The user plays the frames as a short sequence or moves through them with a timeline.
4. Optional comparison tools, such as difference mode, help make changes easier to notice.
5. Frame details and educational guidance help users interpret what they are seeing.

## Challenge test targets

The supplied presentation and interface materials include these five targets:

- **Barnard’s Star**
- **Epsilon Indi B**
- **WISE 0855-0714**
- **RW Aurigae**
- **R Draconis**

## Features described in the presentation

The slide deck describes the following intended or claimed capabilities:

- Time-series image playback
- Image stacking and difference mode
- User-selectable field of view
- Selection of detector / wavelength information
- Gaia DR3 and AllWISE catalogue overlays
- Spectral comparison
- Shareable coordinate parameters in the URL
- Display of observation and image metadata

Refer to the presentation for the proposed processing pipeline and technical architecture.

## Important data and implementation status

**Please read this before presenting the project as a live SPHEREx-data product.**

The supplied labelled-screen document explicitly states that:
- the offline demo frames are **browser-generated simulations**, not real SPHEREx images;
- live mode expects a separate backend endpoint (`POST /api/search`);
- that backend is not included in the supplied interface screenshots/materials;
- connecting and validating archival SPHEREx cutouts is listed as a next step.

The presentation deck describes a more complete data pipeline and several advanced capabilities. The two supplied files do not, by themselves, include the backend source code, prove that every described feature is operational, or provide validation results for real archival cutouts. Verify each capability against the working application before describing it as implemented.

## Technical approach described in the presentation

The presentation identifies this stack and pipeline:

- React + Vite + Nitro
- TypeScript
- IRSA SIA2 for SPHEREx data discovery
- FITS image handling
- WCS projection and alignment
- Gaia DR3 and AllWISE catalogue queries
- Vercel deployment

These are the technologies and components named in the supplied deck; this repository contains presentation/reference materials, not the application source code or a deployable backend.

## Data sources and acknowledgements

The supplied materials refer to:
- NASA/IPAC Infrared Science Archive (IRSA) / SPHEREx
- Gaia DR3
- AllWISE
- WiseView
- NEOSSat and Canadian Astronomy Data Centre resources

**Disclaimer:** Blink Field is an independent hackathon project. NASA does not endorse this project.

## Repository scope

This repository is a **presentation repository** containing the project deck and annotated interface screenshots. It is not the complete application repository. Add the actual frontend/backend source code, setup instructions, tests and deployment details in a separate code repository or in a clearly organised source folder when those materials are ready.

## Before publishing

- [ ] Confirm whether the final project name is Blink Field or SphereBlink.
- [ ] Verify which features work in the current build.
- [ ] Clearly label simulated demo frames.
- [ ] Confirm whether the live SPHEREx backend is connected.
- [ ] Replace any unverified implementation claims with accurate status descriptions.
- [ ] Add the application source code and run instructions if this repository is intended to be the main project repository.
