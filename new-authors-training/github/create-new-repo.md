---
visibility: hidden
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
