---
icon: terminal
order: 950
---

![](/static/github/module-lab-detail.png)

The left hand side of a project is the result of the `english.md` file. The right hand side, "the lab", is the result of the Docker image built during the project creation phase.

The process is advanced and you have a lot of control about how to build your image. But, for now, the only thing you have to know is that ANYTHING that you include in the `notebooks/` directory will be included in the final lab image.

With the exception of `Solution.ipynb` and `activity_solutions_files` that have a special treatment.

### Notebooks
The main notebook you have to worry about for now is `Project.ipynb`, which is the "stripped down/clean" version of your `Solution.ipynb".

### Adding your datasets

Just include your datasets in the `notebooks/` directory. I'd recommend just leaving them in the root of the folder. So, for example, upload the dataset to `notebooks/pokemon.csv`. The `Project.ipynb` notebook will then read it as `pd.read_csv('pokemon.csv')`, as `Project.ipynb` and `pokemon.csv` are in the same directory:

```
notebooks/
    Project.ipynb
    pokemon.csv
```

If you want, you can create a subdirectory, but this is not necessary (actually discouraged for simple datasets) for example:

```
notebooks/
    Project.ipynb
    data/
        pokemon.csv
```

In this case, the notebook will read the file as: `pd.read_csv(data/pokemon.csv)`.

### Special libraries and requirements

If your project uses any libraries outside of the regular stack from DataWars projects, you can include them in the `requirements.txt`

### Advanced usage

!!!danger Advanced users only
This is only intended for advanced projects/users. You probably don't need it.
!!!

The `Dockerfile` contains the steps used to build the lab. You can fully customize this if required. The `docker-compose.yml` can contain special values:


```yml
version: "3.9"
services:
  jupyter:
    build:
      args:
        NB_BASE_IMAGE: datawars/data-analysis-base-3.11:v3  # The base image
      context: notebooks  # The directory used to build your lab
    image: datawars/lab-28959bbcc-pokemon-data-analysis:v1  # The name of the final image
    config: python-jupyter
    # The following attributes are optional and reserved
    # ONLY for advanced users
    command: jupyter nbclassic  # The command to run the container
    x-ram: "1024" # The memory assigned to the container
    x-cpu: 0.5 # The CPU assigned to the container
    x-views:
      - name: Project # The name of the view for the user
        url: "/notebooks/Project.ipynb" # the URL path of the view
        port: "8888" # The port it's running on
    x-envvars:
      - name: MY_SECRET
        value: 123
```
