# Assessment Creation Documentation

---

> *Welcome to the comprehensive guide for creating assessments within the DataWars learning platform. This document serves as your primary resource for understanding the components, best practices, and implementation details essential for developing effective skill assessments.*

## Platform Architecture

### 🏗️ Learning Hierarchy

The DataWars learning platform implements a structured hierarchy that organizes content from broad career paths to specific learning objectives. Each level serves a distinct purpose in the learning journey:

1. Career Path: 

   DataWars organizes learning content into career-focused paths. The Data Analysis career path, for instance, provides a comprehensive learning journey for aspiring data analysts and scientists.

2. Skill Track: 

   Within each career path, skill tracks focus on specific technologies or methodologies. The "Intro to Pandas" skill track, for example, provides a foundational understanding of the Pandas library for data manipulation.

3. Skills:

   Each skill track contains multiple skills that build upon each other. Within the "Intro to Pandas" track, "Pandas Series Basics" represents a fundamental skill that learners must master before progressing to more advanced concepts.

4. Objectives:

   Skills are further broken down into specific, measurable objectives. For the "Pandas Series Basics" skill, objectives include mastering series creation, understanding indexing operations, and implementing various series methods.

### Real-World Example

```
Data Analysis (Career Path)
└── Intro to Pandas (Skill Track)
    └── Pandas Series Basics (Skill)
        └── Objectives:
            1. Understanding Series Creation
            2. Selection and Indexing
            3. Series Methods
```
---
## Assessment Development

### 📊 Assessment vs. Project Distinction

In the context of Pandas Series Basics, the distinction between projects and assessments becomes clear:

1. Coverage
   - A project might focus on series creation and basic operations
   - An assessment evaluates all three objectives: creation, indexing, and methods

2. New Requirements
   - Assessment configuration specifies all three objectives
   - Pages map directly to these fundamental Pandas operations
   - Activities test comprehensive series manipulation skills

### 🛠️ Core Components

### 1. Assessment Configuration Structure

The assessment.json file requires specific configuration fields that define the assessment behavior:

Required Fields:
- `scoring_config`: Determines the scoring methodology
  - Option 1: Per-objective scoring
    ```json
    {
        "scoring_method": "per_objective"
    }
    ```
  - Option 2: Global scoring
    ```json
    {
        "scoring_method": "global",
        "min_global_score_to_pass": 3
    }
    ```
- `objectives`: List of testable objectives
- `expiration_time`: Optional time limit in minutes

Basic Structure Example:
```json
{
    "scoring_config": {
        "scoring_method": "per_objective"
    },
    "objectives": [
        {
            "id": "1",
            "name": "Series Creation",
            "min_points_to_pass": 3
        },
        {
            "id": "2",
            "name": "Series Operations",
            "min_points_to_pass": 4
        }
    ]
}
```

Implementation Example with Repository-Specific IDs:
```json
{
    "scoring_config": {
        "scoring_method": "per_objective"
    },
    "expiration_time": 60,
    "objectives": [
        {
            "id": "tr54a-objective-11",
            "name": "Understanding Series Creation",
            "min_points_to_pass": 3
        },
        {
            "id": "tr54a-objective-22", 
            "name": "Selection and Indexing",
            "min_points_to_pass": 3
        },
        {
            "id": "tr54a-objective-33",
            "name": "Series Methods",
            "min_points_to_pass": 3
        }
    ]
}
```
---

### 📝 Page Attributes in english.md

The english.md file implements specific page attributes that control assessment behavior and objective mapping. These attributes define how content is presented to users and ensure proper evaluation of skills.

Required Attribute:
- `objective`: Maps the page content to specific objectives defined in assessment.json
  - Format: `objective="tr54a-objective-11"`
  - Example: For a page covering Selection and Indexing, use the corresponding objective ID

Optional Attributes:
1. `shuffle-activities`: Randomizes the presentation order of activities within a page
   - Different users see activities in different sequences
   - Helps prevent pattern recognition and memorization
   - Format: Add `shuffle-activities` to page tag

2. `random-sample-amount`: Controls the number of activities shown to each user
   - Specifies maximum activities displayed
   - Format: `random-sample-amount="N"` where N is the desired number
   - Example: `random-sample-amount="5"` shows 5 random activities from the available pool

Example Implementation:

```markdown
# Basic Page with Required Attribute
<page id="dd36e9" 
      name="Understanding Series Creation"  
      objective="tr54a-objective-11">

# Page with All Attributes
<page id="39c4b2" 
      name="Selection and Indexing" 
      objective="tr54a-objective-22"
      shuffle-activities 
      random-sample-amount="3">
```

### english.md Content Implementation

```markdown
<page id="dd36e9" 
      name="Understanding Series Creation"  
      objective="tr54a-objective-11">

# Introduction to Pandas Series
Learn the fundamentals of creating and understanding Pandas Series objects.

<activity id="act1" title="Basic Series Creation">
Create a Series named 'temperatures' with values [98.6, 98.9, 97.8, 99.2]
<correct-answer>pd.Series([98.6, 98.9, 97.8, 99.2], name='temperatures')</correct-answer>
<solution>Use pd.Series() constructor with the name parameter</solution>
</activity>
</page>

<page id="39c4b2" 
      name="Selection and Indexing" 
      objective="tr54a-objective-22"
      shuffle-activities 
      random-sample-amount="3">

<activity id="act2" title="Series Indexing">
Select all temperatures above 98.5 from the 'temperatures' series
<correct-answer>temperatures[temperatures > 98.5]</correct-answer>
<solution>Use boolean indexing to filter values</solution>
</activity>
</page>
```

## Implementation Example

### 📂 Basic Repository Structure

Using our Pandas Series project (lab-tr54a-badge-project-8):

```
lab-tr54a-badge-project-8/
├── assessment.json        # Defines Pandas Series objectives
├── english.md            # Contains Series manipulation activities
└── Project.ipynb         # Provides Series practice environment
```

### Objective ID Convention

The repository name influences the objective IDs:
- Repository: lab-tr54a-badge-project-8
- Objective IDs: tr54a-objective-11 (Series Creation)
- Page references: `objective="tr54a-objective-11"`

## Frequently Asked Questions

1. **Do we need chat.txt file?**

   No, chat.txt is not required for assessments.

2. **How do we handle activities in Project.ipynb?**

   Activity numbers and titles are not needed in Project.ipynb. The notebook should maintain its normal flow without specific activity markers.

3. **Will the docker-compose file configuration change?**

   No, use the same docker-compose configuration as existing projects.

4. **Should we transform existing projects into assessments?**

   No, create new projects instead of modifying existing ones. Each assessment should have its own new repository.

5. **How should we handle activity sampling and shuffling during beta testing?**

   During beta testing phase, do not implement any type of sampling or shuffling functionalities.

6. **How do repository names relate to objective IDs?**
   - Extract prefix from repository name (e.g., "tr54a" from lab-tr54a-badge-project-8)
   - Use format: prefix-objective-number (e.g., tr54a-objective-11)
