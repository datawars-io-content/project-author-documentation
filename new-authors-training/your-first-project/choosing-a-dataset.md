---
icon: database
---

Projects can be configured to use a DataWars Playgrounds data source automatically. Here's a step by step guide to do so.

In this document

* [How to use Playground Datasets in your projects](#how-to-use-playground-datasets-in-your-projects)
* [Examples of projects using datasources](#examples-of-working-projects)

## How to use Playground Datasets in your projects

### 1. Find the data source to use

Data Sources can be either file-based datasets (a CSV, a directory containing image files) or a "device", for example, a MySQL Database.

Let's try to add both.

Go to the [Datasets](https://app.datawars.io/playgrounds?tab=datasets) section of Playgrounds and find the datasets you want to add. In this case I'll add:

- Pagila: a PostgreSQL database containing movie rentals
- Hollywood Movies Database: a CSV file containing hollywood movies data

What you'll need to do is:

1. Go to datasets
2. Find the desired dataset (searching or using the filters on the right)
3. Hover over the logo and you'll see the ID
4. Copy the ID of the data source using the button

![](/static/first-project/datasource-copy-id.png)

In this case, here are the IDs:

- Pagila: `7742f868-902a-4262-bfbe-00497ac27468`
- Hollywood Movies Database: `de5011a1-61fb-45f2-b067-bd363ba012d2`

### 2. Configure your Project's `docker-compose.yml`

Now you have to define in your project's `docker-compose.yml`. There's a new section at the end of the YAML file that is called `x-datasources`:

```yml
# your docker-compose.yml
version: "3.9"
services:
    # list of devices of your project
x-datasources:
    name-of-the-datasource-1:
        id: $ID
    name-of-the-datasource-2:
        id: $ID
```

You can list as many datasources as you want. If the datasource is a "device" type (like the Postgres Pagila one), it'll be automatically added to your project. But, if your dataset is a "file type" (a CSV, a Directory), you also have to configure it in the service that will have access to those files.

Here's a working example with comments:

```yaml
version: "3.9"
services:
  jupyter:
    build:
      args:
        NB_BASE_IMAGE: datawars/data-analysis-nb7-3.11:v1
      context: notebooks
    image: datawars/lab-9059fbffa-example-datasource-project:v1
    x-config: python-jupyter
    x-datasources:
            - hollywood_data # this project will have access to this datasource
x-datasources:
  pagila:
    id: 7742f868-902a-4262-bfbe-00497ac27468
  hollywood_data:
    id: de5011a1-61fb-45f2-b067-bd363ba012d2
```

### 3. Finding the data in the lab

If the data source is a "device type", it'll be in the final lab once you import it, easy.

If the data source is of file type, it'll be mounted in the `/data` directory.


## Examples of working projects

### Python + Pagila (postgres)

This project ([Practice accessing Postres from Python using Pagila](https://app.datawars.io/project/f54d17f2-19db-4221-9bee-7672ac101a11?page=1)) has two devices:

![](/static/first-project/example-datasource-pagila.png)

Here's its `docker-compose.yml`:

```yaml
version: "3.9"
services:
  jupyter:
    build:
      args:
        NB_BASE_IMAGE: datawars/data-analysis-nb7-3.11:v1
      context: notebooks
    image: datawars/lab-0d9f2dd-basic-selects-pagila-python:v1
    x-config: python-jupyter
x-datasources:
  pagila:
    id: 7742f868-902a-4262-bfbe-00497ac27468 # list datasource
```
