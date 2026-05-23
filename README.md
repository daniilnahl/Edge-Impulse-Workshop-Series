# Edge Impulse Workshop Series

A hands-on workshop series for building, training, and deploying small embedded machine-learning models using Edge Impulse Studio and common microcontroller hardware (Arduino Nano 33 BLE Sense). The repository contains step-by-step tutorials, images, and guidance to collect data, design impulses, train models, and deploy to devices.

**Table of Contents**
- [About](#about)
- [Who is this for](#who-is-this-for)
- [What's included](#whats-included)
- [Prerequisites](#prerequisites)
- [Quick start](#quick-start)
- [Tutorials (Parts)](#tutorials-parts)
	- [Part 1 — Getting started & data collection](/Part-1/tutorial-part-1.md)
	- [Part 2 — Impulse design & feature engineering](/Part-2/tutorial-part-2.md)
	- [Part 3 — Training, testing & deployment](/Part-3/tutorial-part-3.md)
- [Project structure](#project-structure)
- [How to use these materials](#how-to-use-these-materials)
- [Citations](#citations)
- [Special thanks](#special-thanks)
- [Questions & Issues](#questions--issues)
- [License & contributions](#license--contributions)

## About
This repository is a workshop-style series that walks you through using the Edge Impulse platform to build embedded ML models. Tutorials combine screenshots, narrative steps, and short code snippets so you can reproduce the exercises on your own hardware.

The materials are intentionally practical and compact so you can complete the basic workflow in a single session:

- Collect data from a phone or device
- Design an impulse (signal processing + learning block)
- Generate features and train a model
- Test, evaluate, and deploy to an embedded target

## Who is this for

This series is aimed at:
- **Students & educators** — quick lab material to teach embedded ML basics.
- **Makers & hobbyists** — practical steps to get a model running on a microcontroller.
- **Embedded engineers & researchers** — short reproducible examples for prototyping.

These tutorials use the Edge Impulse platform (Studio, CLI, and deployment tooling). Useful background and tooling pages:

- Edge Impulse Studio: https://studio.edgeimpulse.com
- Edge Impulse docs: https://docs.edgeimpulse.com
- Arduino Nano 33 BLE Sense (board used): https://store.arduino.cc/products/arduino-nano-33-ble-sense

## What's included

- Tutorial Part 1: Getting started and data collection (images and screenshots)
- Tutorial Part 2: Impulse design, DSP blocks, and feature generation
- Tutorial Part 3: Training, model testing, and deploying to a device
- Example images used in the tutorials (per-part image folders)

## Prerequisites

Before using these tutorials you could get these beforehand (*but each parts requirements are also mentioned in their own files*):

- An Edge Impulse account: sign up at https://studio.edgeimpulse.com
- A development board (recommended): Arduino Nano 33 BLE Sense 
- A modern web browser (Chrome, Firefox, or Safari)
- Optional local tooling for device connections and deployment:
	- Python (for some data-forwarders or scripts) — https://www.python.org/
	- Arduino IDE / Arduino CLI — https://www.arduino.cc/en/software and https://arduino.github.io/arduino-cli/latest/
	- Edge Impulse CLI / daemon — see Edge Impulse docs: https://docs.edgeimpulse.com/docs/cli

Hardware and OS specifics (drivers and toolchain) differ between platforms. Follow the linked documentation for installation and USB/serial driver instructions for your OS.

## Quick start

1. Create an Edge Impulse project at https://studio.edgeimpulse.com and log in.
2. Open the Part 1 tutorial in this repo and follow the instructions:
	 - [Part-1/tutorial-part-1.md](Part-1/tutorial-part-1.md)
3. Continue with Part 2 and Part 3 as you complete each step:
	 - [Part-2/tutorial-part-2.md](Part-2/tutorial-part-2.md)
	 - [Part-3/tutorial-part-3.md](Part-3/tutorial-part-3.md)


## Tutorials (Parts)

- Part 1 — Getting started & data collection
	- Location: [Part-1/tutorial-part-1.md](Part-1/tutorial-part-1.md)
	- Folder with images: [Part-1/Part-1-Images](Part-1/Part-1-Images)

- Part 2 — Impulse design & feature engineering
	- Location: [Part-2/tutorial-part-2.md](Part-2/tutorial-part-2.md)
	- Folder with images: [Part-2/Part-2-Images](Part-2/Part-2-Images)

- Part 3 — Training, testing & deployment
	- Location: [Part-3/tutorial-part-3.md](Part-3/tutorial-part-3.md)
	- Folder with images: [Part-3/Part-3-Images](Part-3/Part-3-Images)

## Project structure

Top-level files and folders:

- `README.md` — this file
- `Part-1/` — step-by-step tutorial and images for Part 1
- `Part-2/` — step-by-step tutorial and images for Part 2
- `Part-3/` — step-by-step tutorial and images for Part 3

Open any of the `tutorial-part-*.md` files to view the workshop content for that part.

## How to use these materials

- Read the Part 1 tutorial first; it covers sign-up, data collection, and creating an impulse.
- Use the example images provided in each Part's image folder if you cannot collect your own data.
- Follow the 'Quick start' and 'Prerequisites' links for installing the CLI/daemon if you want to stream real-time data from a phone or board.
- When training, use the parameters suggested in each tutorial. The screenshots in the tutorials show recommended UI settings and example outcomes.

## Citations

Please cite the following resources when reusing these materials or following the tutorials:

1. Edge Impulse Studio — Edge Impulse. https://studio.edgeimpulse.com
2. Edge Impulse documentation. https://docs.edgeimpulse.com
3. Arduino Nano 33 BLE Sense — Arduino Store. https://store.arduino.cc/products/arduino-nano-33-ble-sense
4. Arduino IDE & CLI — Arduino. https://www.arduino.cc/en/software & https://arduino.github.io/arduino-cli/latest/
5. Node.js — Node.js Foundation. https://nodejs.org/
6. Python Programming Language. https://www.python.org/

If you reproduce figures or screenshots from Edge Impulse Studio in other publications, please credit Edge Impulse and link to the Studio or the specific docs page used.

## Special thanks

Special thanks to the Edge Impulse team for providing Edge Impulse Studio, the documentation, and example workflows that make this workshop possible.

## Questions & Issues
If you encounter any bugs or have feature requests, please open an issue in this [GitHub repository](https://github.com/daniilnahl/Edge-Impulse-Workshop-Series). For networking, collaboration, or other inquiries, feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/daniil-nahliuk-4213aa322/).

## License & contributions

**License:** This workshop is licensed under the **[Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)**.

### What you can do:

**Share**: copy, redistribute, and use these materials for any purpose (including commercial).  
**Adapt**: modify, remix, and build upon the workshop for your own courses or tutorials.  
**Attribute**: give credit to the original creator (required).

### How to attribute:

When you use or adapt this workshop, please see the [LICENSE](LICENSE) for attribution examples and the full license text.

### Contributing:

Contributions are welcome! To improve these materials, please open an issue or submit a pull request in the repository. By contributing, you agree that your contributions will be licensed under the same CC BY 4.0 license.

