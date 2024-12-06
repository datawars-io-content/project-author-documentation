---
title: Project Testing Guide for New Testers
tags:
  - Testing
  - Quality Assurance
  - Project Review
  - Guide
icon: bug
---


# Project Testing Guide for New Testers

First go through [Good Practices for Project Authoring](/new-authors-training/your-first-project/good-practices-to-follow.md).


## The "Detective's Mindset" for Testing

Imagine you are a detective, stepping into a mysterious case. The project before you is like a crime scene - every detail matters. Typos are the dropped breadcrumbs, unclear instructions are the smudged fingerprints, and incorrect solutions? They’re the smoking gun. With your magnifying glass in hand and an insatiable curiosity, your job is to uncover every imperfection, every inconsistency, and every missed opportunity. 

You revel in the thrill of discovery. There’s nothing quite like the satisfaction of finding a flaw no one else noticed. Below are the ways in which you can do so:


## Areas to Target Relentlessly

### 1. **Spelling and Grammar Mistakes**
   - **What to Look For**: Spelling and grammar errors are easy catches, and even one mistake can leave a bad impression.
   - **Why it Matters**: Poor language skills make the project look unpolished and can frustrate users.
   - **Your Task**: Review every sentence carefully. Hunt down each misspelling, typo, or awkward phrase. Don't let them slip up on the basics.

### 2. **Relevance and Accuracy of Introductory Content**
   - **Objective**: Make sure that the **Introduction** section and `public.md` are on-topic and give a clear overview of the project. `public.md` is the first thing a user sees before starting the project.
   - **Checklist**:
     - Is the introduction relevant to the actual project content? Look for any vague language or misleading details.
     - Ensure that all information is correct and aligned with the project's purpose. Set the standard for a strong first impression.
   - **Introduction** and `public.md` are visible at following places in the project.
   ![Introduction](/static/project-testing-images/introduction.png)
   ![public.md](/static/project-testing-images/public-md.png)

### 3. **Activity Descriptions**
   - **Purpose**: The activity description should leave no room for confusion or misinterpretation.
   - **What to Watch For**:
     - **Clarity**: If you see dense, jargon-filled paragraphs, insist they simplify. No user should feel lost while reading.
     - **Conciseness**: A description should be as short as possible while still clear. If long explanations are necessary, they should be broken into bullet points.
     - **Completeness**: Are the instructions thorough? If any step or detail is vague or missing, report it. Authors should know that clarity is non-negotiable.

### 4. **Expected Outcome**
   - **Importance**: Users rely on a clear expected outcome to see if they're on the right track.
   - **What to Verify**:
     - Check that the expected outcome exactly matches the solution. There's no room for "almost."
     - If results might vary due to a solution that results in dynamic result, ensure there's a **note** explaining this. Users should know what to expect or how to judge their answers if they differ from the example.
   - The example below demonstrates the correct expected outcome.
   ![Correct Expected Outcome](/static/project-testing-images/expected-outcome-match.png)

### 5. **Solution Quality and Explanation**
   - **Goal**: A solution should do more than just provide an answer - it should make the answer understandable.
   - **Essentials**:
     - **Code Comments**: Ensure the solution code is well-commented so each step is clear. If anything is unclear, insist on explanations.
     - **MCQ Activities**: For multiple-choice questions, a simple correct answer isn't enough. Users need to understand *why* an answer is correct. If the explanation is missing, it's an issue.
   - The screenshot below illustrates an incorrect way of presenting a solution to the user. While it provides the final answer, it fails to show the necessary steps to arrive at that conclusion, leaving the user without proper guidance.
   ![Bad Solution](/static/project-testing-images/solution-bad.png)


### 6. **Jupyter Notebook Content**
   - **Objective**: The Jupyter notebook should be carefully crafted to guide users without giving away answers.
   - **What to Look For**:
     - Ensure there are no hints or solutions provided within the notebook that the authors didn't intend to reveal. 
     - Check that there are appropriate placeholders or empty code cells for users to fill in their own answers. This helps users engage actively.
   - In the following example, the author has left a hint in the Jupyter notebook. This is an issue.
   ![Hint or solution should not be present in the jupyter notebook.](/static/project-testing-images/hint-bad.png)
   - The example below highlights the absence of placeholders in the Jupyter notebook, which can lead to confusion.
   ![Absence of proper placeholders](/static/project-testing-images/placeholder-bad.png)
   - After adding placeholders in the previous example, we get clear, complete and easy to follow activities.
   ![Correct Placeholders](/static/project-testing-images/placeholder-good.png)


## Is It Enough?

After meticulously investigating and uncovering every flaw in the project, you might feel a surge of accomplishment. But after a while, the thrill of finding errors alone starts to fade. The case doesn’t feel closed. Something is missing.

You’ve exposed every clue, but you haven’t solved the whole mystery. Instead of stopping at fault-finding, consider what a truly great detective would do: collaborate with the "suspects" to rewrite the story. Help the project authors understand not just *what* went wrong but *why* it went wrong and *how* to fix it. Debug their code, offer insights, and provide actionable feedback that saves them time and effort.

When you take this approach, you’re no longer just a critic - you’re a partner.


## How to Report Issues?

The following video serves as guide on how to report issues on the platform.

[!embed](https://www.loom.com/embed/3cd3650f5269449fa721a92507955b99?sid=315499f5-080d-4fcb-b9a1-02dc2207b6c7)
