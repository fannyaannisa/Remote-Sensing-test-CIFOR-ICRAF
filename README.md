# Ngemplak_Land Cover_2018
Repository Contents
- README.md: This file, outlining the project overview, implementation steps, encountered challenges, and proposed solutions.
- Ngemplak_LandCover_2018.js: A customized Google Earth Engine (GEE) script developed for land cover classification within the Sepaku watershed, using publicly available reference data and Landsat 8 imagery.

1. Overall Plan
My strategy to complete this geospatial data processing task was divided into four main stages:

Setup and Scoping: Create a new GitHub repository. Carefully analyze the original project structure and the GEE script to understand dependencies, data sources, and the classification workflow.

Adaptation for AOI and Time Period: Redefine the Area of Interest (AOI) to focus on the Sepaku sub-watershed in East Kalimantan. Update the script to filter Landsat 8 Surface Reflectance imagery for the year 2018.

Blocker Identification and Resolution: Address issues caused by private GEE asset paths. Replace inaccessible assets (e.g., users/hadi/REF_INDO_2019) with equivalent, publicly available CSV data that can be uploaded to Earth Engine (e.g., point samples with lat/lon and land cover labels).

Documentation and Finalization: Log all actions, technical decisions, and issues in this README. Clearly distinguish between what was achieved independently and what would require collaboration or domain-specific support.

2. Steps Taken (3-Hour Work Log)
- Hour 1: Project Setup & Initial Review
15 min: Initialized the GitHub repository and structured it with a basic layout (README, GEE script).

25 min: Reviewed the original reference materials and dataset. Determined that the classification approach uses Random Forest and predictor variables including NDVI, NDBI, and spectral bands.

20 min: Analyzed the legacy GEE script. Identified key hardcoded paths, such as private assets and modular require() imports that must be bypassed for portability.

- Hour 2: AOI Setup & Code Adaptation
10 min: Defined the Sepaku AOI using a bounding box polygon in the GEE script.

30 min: Merged essential functions from the modular structure into a standalone script to simplify execution and remove external dependencies.

20 min: Converted CSV reference data (e.g., samplesLocation.csv) into a GEE asset by uploading it and defining geometry columns (longitude, latitude) correctly.

- Hour 3: Final Integration & Documentation
25 min: Finalized imagery filtering, masking, and variable creation. Replaced inaccessible references with placeholders pointing to personal GEE assets.

35 min: Composed this README file to capture the logic, choices, obstacles, and lessons from the task. Ensured that others can follow the script structure and reproduce results with minimal setup.

3. Challenges Encountered
- Limited training data for Kec. Ngemplak Boyolali in 2018
While attempting to use the reference dataset for the Kecamatan Ngemplak in 2018, I discovered that very few (or no) training points were available within my AOI for that year. This made it impractical to proceed with meaningful classification for 2018.
- difficulty finding the assets needed to process the data

4. Proposed Solutions
Individual Approach (The strategy I implemented)
As an individual contributor, the most effective approach is to rebuild the necessary components using publicly available data and create a self-contained workflow.
- Re-create the Reference Data Asset
Action: Download the reference data from the public Figshare link. Upload this data (e.g., CSV) to a personal GEE asset folder. Then, replace the private asset path in the GEE script with the new, accessible path.
- Define a Custom AOI
Action: Use the GEE geometry tools to manually define a new AOI covering the Kec. Ngemplak region. For a more formal approach, one could find a public feature collection of administrative boundaries (e.g., from FAO GAUL or GADM).
