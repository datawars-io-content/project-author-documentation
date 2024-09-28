---
icon: mortar-board
title: Good Practices for Project Authoring
description: Guidelines to create engaging and effective projects.
---

# Good Practices for Project Authoring

When designing a project, it’s crucial to keep two primary goals in mind:

1. **Avoiding Boredom**  
2. **Preventing Exhaustion**

The following guidelines will help you meet these goals effectively.

## 1. Define and Manage Project Scope

A well-defined **scope** is essential to ensure users face challenges that match their skill level and progress gradually. Understanding what the users already know and what they’re expected to learn is key.

For example, if you're creating a project within the **Data Cleaning with Pandas** skill track, asking users to perform a simple task like creating a `Series` from a column in a `DataFrame` may lead to boredom as it lacks sufficient challenge. Conversely, asking them to perform complex operations like merging datasets before covering the necessary concepts may overwhelm them. Ensure each project aligns with the skills already covered to keep users engaged without frustration.

## 2. Format Titles and Descriptions Thoughtfully

- **Activity Titles**: Always frame titles as questions to engage the user. For example, instead of “Capital of Argentina,” use “What is the Capital of Argentina?” This sparks curiosity and primes the user for problem-solving.

- **Activity Descriptions**: Ensure that descriptions are clear, concise, and well-structured. Avoid long blocks of text, as they can overwhelm users, especially those juggling full-time work or study alongside their learning. Most users are looking to learn Data Science through hands-on coding exercises, so lengthy descriptions can exhaust them and make the project less enjoyable.

  - Use **bold** or *italics* to emphasize key points.  
  - Enclose code elements (e.g., variable or column names) in backticks (\`) to distinguish them from text.  
  - Use triple backticks (\`\`\`) for code blocks to improve readability.

If you can’t avoid lengthy descriptions, such as in **capstone projects**, try breaking the task into smaller activities. If that’s not feasible, use tools like ChatGPT to improve clarity and structure.

**Example Prompt**:  
*You are a data science professor. I need your help improving the formatting and clarity of my activity descriptions. I'll provide the title and description, and you will revise them.*

Example: Notice how ChatGPT transformed the activity title and description.

Before:  
![Activity Before Formatting](/static/good_practices_images/best_practices_prompt_1.png)

After:  
![Activity After Formatting](/static/good_practices_images/best_practices_prompt_2.png)

- **The Activities Should Be Atomic**: One major drawback of longer activity descriptions is that they often lead to multiple steps within a single task. This complexity makes it harder to test and pinpoint errors. If an activity fails, users may not know where they made a mistake. For example, consider the following activity that requires users to complete four steps: calculating `common_chatbots`, defining the `fill_chatbot` function, applying this function to the `chatbot_name` column to impute missing values, and filling any remaining missing values with the string `"Unknown"`. If the task fails, users might struggle to identify the specific step where they made an error.

![Not an Atomic Activity](/static/good_practices_images/good_practices_atomic_activities.png)

## 3. Use Placeholders in Jupyter Notebook

Provide placeholders whenever users are asked to complete an activity. For example, if they need to store results in a variable or create a new column in a `DataFrame`, placeholders help guide them. This minimizes confusion and helps keep the task focused.

Examples of placeholders:  
![Variable Placeholder](/static/good_practices_images/best_practices_placeholder_var.png)  
![Column Placeholder](/static/good_practices_images/best_practices_placeholder_col.png)
![Function Placeholder](/static/good_practices_images/best_practices_placeholder_func.png)

## 4. Provide a Preview of Expected Outcomes

Where possible, include a preview of the expected result. For example, in a visualization project, show the desired plot, or when manipulating a `DataFrame`, provide a snapshot of the expected output. These visual or textual cues help users understand what the end goal looks like, reducing frustration and ensuring they are on the right path.

Examples:  
![Expected Outcome DataFrame](/static/good_practices_images/best_practices_exp_1.png)  
![Expected Outcome Visualization](/static/good_practices_images/best_practices_exp_2.png)

## 5. Practice Empathy

Think from the user’s perspective and ask:

- What might confuse or challenge the user at this stage?  
- Are the instructions clear for someone with the expected level of knowledge?  
- Would I feel confident completing this task, given what I’ve learned so far?

Empathy-driven design leads to a smoother learning experience by anticipating user needs.

Example:  
![Example Activity](/static/good_practices_images/best_practices_empathy_1.png)

Consider the activity in the screenshot above where users are asked to input answers. If they can't solve it and request a solution, they receive the correct value to pass. But pause and think—what was on their minds?

The users requested help because:

* They wrote code but got the wrong result, or  
* They didn’t know how to approach the problem.

In both cases, just giving the answers isn’t enough. They expect to learn how to solve the problem. The solution should include code or explanations demonstrating the correct process, reinforcing their learning for future tasks.

## 6. Anticipate and Address Edge Cases

Be mindful of edge cases and provide detailed instructions to address them. Whenever an edge case arises, clearly outline the steps users should follow to handle it. This prevents users from feeling stuck or confused when encountering unexpected situations. 

For example: Look how different ways of calculating frequency counts result in different order of index when their values are equal. In this case, we should mention in the activity description that the user should use `value_counts()`.

![Edge Case Example](/static/good_practices_images/best_practices_edge.png)

## 7. Manage Time Expectations and Feedback

Consider the time required to complete the project. For **Learn** and **Practice** projects, aim for 25–30 minutes, while for **Assignments** and **Capstone Projects**, a duration of 45–60 minutes is ideal. Managing time expectations ensures the project remains engaging and manageable without overwhelming users.

---

By following these best practices, you’ll create projects that are engaging, appropriately challenging, and enjoyable for learners. This balance will help keep users motivated and make their learning experience both rewarding and frustration-free.
