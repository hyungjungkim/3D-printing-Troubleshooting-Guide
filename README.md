# 3D Printing Troubleshooting Guide
A categorized dataset of 3D printing failures and defects for AI-based quality inspection and troubleshooting research

## Motivation
As manufacturing undergoes a rapid digital transformation, Large Language Models (LLMs) are becoming pivotal to automating complex decision-making. In Additive Manufacturing (AM), however, the transition to fully autonomous quality control is hindered by a critical bottleneck: the lack of high-quality, labeled failure datasets. While Fused Deposition Modeling (FDM) is the most accessible 3D printing technology, troubleshooting remains a manual, trial-and-error process for many. This repository presents the 3D Printing Troubleshooting Guide, a curated dataset that bridges this gap. By providing structured data on defects and solutions, we aim to empower LLMs and machine learning models to perform real-time error detection and autonomous troubleshooting, turning domain-specific knowledge into actionable AI.

## Dataset description
This dataset was manually curated from technical documents on the 3D printing process and output quality issues. The following are source websites:
* [Simplify3D](https://www.simplify3d.com/resources/print-quality-troubleshooting)
* [Prusa3D Help](https://help.prusa3d.com/category/print-quality-troubleshooting_225)
* [All3DP](https://all3dp.com/1/common-3d-printing-problems-troubleshooting-3d-printer-issues)

### Creation details
The original technical documents were reviewed in full, redundant entries were consolidated, and irrelevant links and unnecessary examples were removed.

* Content: Each entry consists of three components
  * Problem – Description of the print quality issue
  * Cause – Identified or potential reasons for the issue
  * Solution – Recommended corrective actions
* Format: The dataset is provided in both Markdown and PDF formats for flexible use in machine learning and information retrieval research.
  * [3D-Printer-Troubleshooting-Guide-Markdown.md](3D-Printer-Troubleshooting-Guide-Markdown.md)
  * [3D-Printer-Troubleshooting-Guide-PDF.pdf](3D-Printer-Troubleshooting-Guide-PDF.pdf)

### Sample contents
    ...
    2. Not Sticking to the Bed
    
    1) Build platform is not level
    Many printers include an adjustable bed with several screws or knobs that control the
    position of the bed. If your printer has an adjustable bed and you’re having trouble
    getting your first layer to stick to the bed, the first thing you will want to verify is that
    your printer’s bed is flat and level. If the bed is not level, one side of your bed may
    be too close to the nozzle, while the other side is too far away. Achieving a perfect
    first layer requires a level print bed.
    ...

## Original publication
(To be added.)

## Download
This dataset can also be downloaded directly from the following repositories:
* [Mendeley data](https://data.mendeley.com/)

## License
This dataset is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

## Contact
Please email Jingu Kang (jingu1138@konkuk.ac.kr, co-creator), Kangmin Ahn (akm5587@konkuk.ac.kr, co-creator), or Hyungjung Kim (hyungjungkim@konkuk.ac.kr, maintainer) for any questions regarding the dataset.

<img src="images/konkuk_university.png" height="45"/>
