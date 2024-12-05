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

First go through [Good Practices for Project Authoring](../new-authors-training/your-first-project/good-practices-to-follow.md).


## The “Professor’s Mindset” for Testing

Imagine you are a 55-year-old college professor. You’ve dedicated decades to teaching science and engineering, watching your peers achieve recognition and make meaningful contributions to their fields. Yet, despite all those years, your name remains unknown. Quietly, you’ve begun to accept that perhaps you will never accomplish much. But surely, there must be a way to fill this void—a way to feel important, even if it means elevating yourself at others’ expense. And who better to target than your students?

They’re inexperienced, uncertain, and easy to manipulate. By making concepts deliberately complex, by assigning impossible workloads, by reveling in their confusion, you can convince yourself that your own intellect towers above theirs. After all, if your students struggle to understand, then you must be brilliant, right? You may not be celebrated in journals or accolades, but here, within your classroom, you wield control and power—the kind that makes you feel superior, even if it’s at the cost of others' misery.

In this case, you are the professor and project authors are your students. You cannot let them have an easy life. Below are the ways in which you can do so:


## Areas to Target Relentlessly

### 1. **Spelling and Grammar Mistakes**
   - **What to Look For**: Spelling and grammar errors are easy catches, and even one mistake can leave a bad impression.
   - **Why it Matters**: Poor language skills make the project look unpolished and can frustrate users.
   - **Your Task**: Review every sentence carefully. Hunt down each misspelling, typo, or awkward phrase. Don’t let them slip up on the basics.

### 2. **Relevance and Accuracy of Introductory Content**
   - **Objective**: Make sure that the **Introduction** section and `public.md` are on-topic and give a clear overview of the project. `public.md` is the first thing a user sees before starting the project.
   - **Checklist**:
     - Is the introduction relevant to the actual project content? Look for any vague language or misleading details.
     - Ensure that all information is correct and aligned with the project’s purpose. Set the standard for a strong first impression.

### 3. **Activity Descriptions**
   - **Purpose**: The activity description should leave no room for confusion or misinterpretation.
   - **What to Watch For**:
     - **Clarity**: If you see dense, jargon-filled paragraphs, insist they simplify. No user should feel lost while reading.
     - **Conciseness**: A description should be as short as possible while still clear. If long explanations are necessary, they should be broken into bullet points.
     - **Completeness**: Are the instructions thorough? If any step or detail is vague or missing, report it. Authors should know that clarity is non-negotiable.

### 4. **Expected Outcome**
   - **Importance**: Users rely on a clear expected outcome to see if they’re on the right track.
   - **What to Verify**:
     - Check that the expected outcome exactly matches the solution. There’s no room for “almost.”
     - If results might vary due to a solution that results in dynamic result, ensure there’s a **note** explaining this. Users should know what to expect or how to judge their answers if they differ from the example.

### 5. **Solution Quality and Explanation**
   - **Goal**: A solution should do more than just provide an answer—it should make the answer understandable.
   - **Essentials**:
     - **Code Comments**: Ensure the solution code is well-commented so each step is clear. If anything is unclear, insist on explanations.
     - **MCQ Activities**: For multiple-choice questions, a simple correct answer isn’t enough. Users need to understand *why* an answer is correct. If the explanation is missing, it’s an issue.


### 6. **Jupyter Notebook Content**
   - **Objective**: The Jupyter notebook should be carefully crafted to guide users without giving away answers.
   - **What to Look For**:
     - Ensure there are no hints or solutions provided within the notebook that the authors didn’t intend to reveal. 
     - Check that there are appropriate placeholders or empty code cells for users to fill in their own answers. This helps users engage actively.


## Is It Enough?

After rigorously testing and pointing out every error in the project, you might still feel something is missing. Catching mistakes gave you a sense of accomplishment, but it’s starting to feel hollow. Watching the authors struggle at first brought some satisfaction, but now you see that this alone isn’t fulfilling. You risk being seen as harsh or unsympathetic.

But there is another way to leave your mark, to redeem yourself: become a guide, not just a critic.

Instead of only pointing out errors, help the authors understand *why* they’re wrong. Pinpoint the exact areas where they could improve and even go a step further: **debug their code** and identify potential improvements.

When you offer constructive solutions, you’re not just a tester—you’re a collaborator. By saving authors time, you enable them to produce better projects faster. This way, you’ll find a deeper satisfaction, knowing you’re leaving a lasting, positive impact—not just finding faults but also creating solutions.


## How to Report Issues?

The following video serves as guide on how to report issues on the platform.

[!embed](https://www.loom.com/embed/3cd3650f5269449fa721a92507955b99?sid=315499f5-080d-4fcb-b9a1-02dc2207b6c7)
