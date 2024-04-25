---
icon: hubot
order: 800
---


# chat.txt

The `chat.txt` file contains the context that will be passed to the AI assistant whenever the student asks a question. It should have the following structure:

```
The objectives of the project are:
* Objective 1
* Objective 2
* Objective 3

The data the student has...

[DESCRIPTION ABOUT THE DATA]
```

The learning objectives are related to the skill your project covers. You can be more specific providing more details. For example, if you're working on Filtering and Sorting with Pandas, but your project heavily relies on boolean operators, you can be more specific and add:

```
The objectives of the project are:
* Filter rows of the dataframe using boolean operators &, | and ~.
* Filter rows of the dataframe using the query method including boolean operators (`and`, `or`, `not`)

```

The description of the data should be the characteristics of the data the student is dealing with. **Be AS BRIEF as possible, as this counts towards the total TOKEN Count and is MORE EXPENSIVE**. For example:


If your data is a tabular file (a CSV, dataframe), you can use the `df.info()` methods and just print the `df.head().to_markdown()`.

If your data is a database, you can just tell the agent that "the student is working with the MySQL Sakila sample database".
