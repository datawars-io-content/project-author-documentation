---
icon: question
title: Knowledge Tests
description: Guidelines to create Knowledge Test.
---

# Knowledge Tests

Knowledge tests are designed to gauge a user's understanding of fundamental, technical, and practical knowledge within a given skill.

## Structure of a Knowledge Test

Each knowledge test consists of three types of multiple-choice questions:

### 1. Conceptual Questions
These questions assess the user's understanding of the core concepts of a skill. They are language-agnostic and focus on theoretical knowledge.

Example:
```
What's the efficiency of the membership operation of a dictionary in python? (eg: `"a" in my_dict`)

- O(1) # correct
- O(n)
- O(log n)
- O(n ** 2)
```

### 2. Syntactical Questions
These questions test the user's knowledge of syntax used in coding. They are specific to programming languages and help evaluate familiarity with code structure and rules.

Example:
```
In `pd.merge`, what's the name of the parameter used to specify the type of merge that will be performed (`inner`, `outer`, etc)?

- `how=` # correct
- `join=`
- `on=`
- `inner=`
```
```
What's the name of the Scikit Learn function used to separate testing and training data?

- `train_test_split` # correct
- `test_split_train`
- `split_train_test`
- `split_test_train`
```

### 3. Scenario-Based Questions
These questions present a real-world scenario with associated dummy data. They simulate practical applications of the skill, requiring users to apply their knowledge in realistic situations.

Example:
```
Suppose you have two dataframes, `movies` and `directors` with the following structures:

movies:

movie_id |   title     | director_id
------------------------------------
819      | Top Gun     |   3
133      | Man on Fire |   3

directors:

id(*) |     name     | nationality
-----------------------------------
91    | Tony Scott   |   US
12    | Ridley Scott |   US


How should we merge them to achieve the following result:

movie_id |   title     | director_name | director_nationality
--------------------------------------------------------------
819      | Top Gun     |   Tony Scott  |        US
133      | Man on Fire |   Tony Scott  |        US


- `movies.merge(directors, how='left', left_on='director_id', right_index=True)` # correct
- `movies.merge(directors, how='outer', left_on='director_id', right_index=True)`
- `movies.merge(directors, how='outer', left_on='director_id', right_on='id')`
- `directors.merge(movies, how='outer', left_on='director_id', right_on='id')`
```

## Guidelines for Creating Questions

When designing knowledge test questions, follow these rules:

- One or more options may be correct.
- Each question must be relevant to the skill being tested.

## Example Questions & Structure

Examples of different question types and the `english.md` structure can be found in this repository: [Intro to Pandas for Data Analysis - Knowledge Test](https://github.com/datawars-io-content/knowledge-test-intro-to-pandas)

### Structure of `english.md`

Each question type is documented on a separate `page`, with relevant activities written within those pages. Below is the general structure:

```
<page id="" name="Conceptual Questions">
    <!-- Activities related to conceptual questions -->
</page>

<page id="" name="Syntactical Questions">
    <!-- Activities related to syntax-based questions -->
</page>

<page id="" name="Scenario Questions">
    <!-- Activities related to scenario-based questions -->
</page>
```
