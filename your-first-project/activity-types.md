---
icon: issue-closed
order: 700
---

Here are the different activity types you can include in your project:

### Input activities

![](/static/first-project/input-activity.png){width=600}

Input activities give the user a blank field to enter their answer. It can be a numeric answer, or a text answer. For example:

* `How many null values are in the column X?`: The answer is numeric, integer `250`
* `What's the mean of the column X?` The answer is numeric, but a float: `25.80`.
* `What's the most common city in the dataset?` The answer is a string `New York City`.

!!!warning Float and String values
Float and string values are checked EXACTLY as they're provided. Strings are CASE SENSITIVE. And for floats, read the note below:
!!!

If your input activity's correct answer is a float, make sure you explain the user how many decimal values you're considering as valid, providing examples. Example:

```
What's the mean of the column X?
Enter the value with 2 decimal places. For example, if you find the value to be `82.35823`, enter only `82.35`
```

### Multiple choice activities

![](/static/first-project/multiple-choice-activity.png){width=600}

Multiple choice activities are as simple as they get. They can be configured to have one or more correct values (the widget rendered will be a radio button or a checkbox, respectively).

### Code activities (without input)

![](/static/first-project/no-input-code-activity.png){width=600}

"Code" activities are designed to check something from the user interactively. They're advanced types of activities and apply to MORE than just Jupyter activities. Internally, we can run custom code to check that the user's code passes the grading provided.

### Code activities (with input)

![](/static/first-project/input-code-activity.png){width=600}

Similar to a regular code activity, the user has to provide some input that is evaluated dynamically.
