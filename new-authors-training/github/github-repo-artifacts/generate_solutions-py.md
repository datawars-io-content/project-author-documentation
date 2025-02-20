---
icon: code
title: Generate Dynamic Solution Files
description: Guidelines to generate solution files every time an update is pushed to the repo.
---


# generate_solutions.py

Hi everyone! I wanted to share a finding with you regarding our ongoing update of the base images for our labs (including updating pandas, numpy, matplotlib, and other packages). We've encountered an issue related to the activity solution files, particularly with Matplotlib, though it could apply to other files as well.

For instance:  
If we create a solution image using Matplotlib version 3.9.0 and later update the lab with the latest version, 3.10.0, we face a problem. When comparing the solution image we created (with version 3.9.0) to a user’s solution image (which uses version 3.10.0), the images will look identical, but the user won't pass the assertion due to version differences.

### Possible Solution:  
We’re considering generating dynamic solution files. Each time we push changes to the project on GitHub, the solution files will be automatically regenerated. This way, the solution files will always match the latest version of the packages in the lab.

Here’s what we have done in this repo: https://github.com/datawars-io-content/lab-843g8gf-plotting-basics-hotel-rating-trip-types

1. **New `generate_solutions.py` file**:  
   We have added a new file in the `notebooks/` directory called `generate_solutions.py`. This file contains all the code from the `Solution.ipynb` notebook and generates the activity solution files. The code must contain same activity solution file names that are used in `english.md`.
  ![Location of generate_solutions.py](/static/github/github-repo-artifacts/generate_solution-py.png)

2. **Dockerfile Update**:  
   In the `notebooks/` directory, We have updated the Dockerfile to include:  
   `RUN [ -f generate_solutions.py ] && python generate_solutions.py`  
   This ensures that new solution files are created every time we push an update to the GitHub repo.
  ![Dockerfile contents](/static/github/github-repo-artifacts/Dockerfile.png)