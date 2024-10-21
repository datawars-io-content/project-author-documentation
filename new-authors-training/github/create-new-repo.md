---
icon: code-square
order: B
---

# Creating a new repository for your project

1. Create a new repository using the + sign.

![new-repo-button](../../static/creating-new-repo/new-repo-button.png)

2. Select the template

Depending on your project, you can choose jupyter template or the sql template.

![select-template](../../static/creating-new-repo/select-template.png)

3. Write the repository name

Format of the repository name: `lab-{random ID}-{project_name}`

* Random ID can be of any number and alphabets except special characters without any spaces.
* The project name should be in small case separated by `-` or `_` (dash or underscore).

> Example: `lab-1234-credit-card-fraud-detection` 

![write-repo-name](../../static/creating-new-repo/write-repo-name.png)

>    Make sure do not put any characters before `lab-` and after the project name.


4. Now, click on the Create repository button.

	This is how your repository looks.

    ![new-repo](../../static/creating-new-repo/new-repo.png)

> **Depending on the project, you can choose the template. For the SQL project, you can choose the SQL template.**

For your SQL projects, you have to setup the `docker-compose.yml` file. You can refer to the [Available Databases](https://github.com/datawars-io-content/reference-databases-available-sql-tracks) for the list of databases available. 

Check the `.yml` file in the repository and change the `docker-compose.yml` file according to the database you want to use.

> Check this document on how to find dataset from datasources playground: [Finding Datasets from Datasources Playground](https://datawars-io-content.github.io/project-author-documentation/new-authors-training/your-first-project/choosing-a-dataset/)

When you select the dataset from the datasources playground, you can get the name of the database and ip address of the database from the `docker-compose.yml` file and you can include the same in the `english.md` file.

* **Data path**: Mention the path of the dataset. This is important as it helps in locating the dataset easily.

- For data files with CSV file format, the path can be mentioned as follows: **{{datasource.filesystem_path}}/"filename"**
- For databases, the ip address path can be written as follows: **{{devices_copy."Data Source".ip_address}}**
![Dataset path](/static/creating-datasets-img/image-2.png)

> Thing to consider while writing data sources path: 

Here is the path to get `ip address` of devices rendered in description. 
```markdown
{{devices."{Device Name}".ip_address}}
```

For Example: 

1. In case device name is `Postgres Airlines demo database`, the path will be: 
```markdown
{{devices."Postgres Airlines demo database".ip_address}}
```
![Data Source Path](/static/creating-datasets-img/image-10.png)

2. In case device name is `Data Source`, the path will be: 
```markdown
{{devices."Data Source".ip_address}}
```
![Data Source Path](/static/creating-datasets-img/image-9.png)

Here is the explample:

- Example of `english.md`: [Querying Logical Operator with Airlines using Python](https://github.com/datawars-io-content/lab-87dg27-advance-sql-logical-operator-airlines/blob/master/english.md?plain=1#L10)
- Example of `docker-compose.yml`: [Querying Logical Operator with Airlines using Python](https://github.com/datawars-io-content/lab-87dg27-advance-sql-logical-operator-airlines/blob/master/docker-compose.yml)
