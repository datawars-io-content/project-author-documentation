---
icon: markdown
order: 1000
---

[!embed](https://www.loom.com/embed/b317af55911648ba894c96ec69d240d0?sid=f2ebb0bf-f4ad-45dd-9116-116b698e4d9e)

# english.md

The `english.md` file defines the content on the left panel of a project. It's a markdown file with special HTML tags defined by us. The main tags you have to know are `<page>` and `<activity>`. All tags must contain a UNIQUE ID (unique within the project).

You don't have to manually code the tags, as we have VSCode snippets that will make your life easier.

[!file Download Snippets](/static/github/user-snippets.json)

### Pages

Pages are MANDATORY and where all the other elements live. You can have as many pages as you want and they define the big "sections" on the left side panel. They can contain any markdown text or images you want to add as well as activities.

![](/static/github/pages-left-menu.png)

Pages are defined with the syntax:

```html
<page id="{ID}" name="{TITLE OF THE PAGE}">
</page>
```

![](/static/github/page-mapping-code.png)

### Activities

Activities live within a `<page>` component. Depending on the activity type, they'll support special attributes and internal tags. But they all have a `title` attribute, and they support any text as a description:


```html
<page id="82b82" name="Warm up activities">
<activity title="Find the most powerful pokemon" ... other attributes ...>

<<  This is the description of the activity >>
Find the most powerful by `Attack` attribute. Check the following image as an example.
![](images/powerful_pokemon_activity.png)

<hint>
# hint
</hint>

<solution>
# solution
</solution>

</activity>
</page>
```

As you can see from above, the activity description accepts any valid markdown code, including images.

All activities must contain the `<hint>` and `<solution>` tags. But you can leave them empty if you don't want to provide a hint/solution, as these are optional (although strongly recommended).

Specific activity types:

#### Input activities

Input activities ask the user for their answer by rendering a simple input widget. Here's the syntax:

```html
<activity id="8b1372ac" title="How many null/missing values has the column `FoodCourt`?" type="input">

<correct-answer>183</correct-answer>
<hint>
Try the `isna()` method.
</hint>
<solution>
The simplest solution is just to use the `.isna()` which returns a boolean array. The `.sum()` method of the boolean array will give you the final answer:

    ```python
    >>> df['FoodCourt'].isna().sum()
    183
    ```

</solution>
</activity>
```

When the user submits their answer, we check if the answer matches whatever you specified in `<correct-answer>`.

![](/static/github/input-activity-mapping-code.png)

#### Multiple choice activities

Here's the syntax of a multiple choice activity:

```html
<activity id="c29c52" title="What's the result of `2+2`?" type="multiple-choice" widget="radio">

Do the quick math and answer.

<answer id="15ce4e" is-correct>`4`</answer>
<answer id="46f882">`3`</answer>
<answer id="8b12c">`2`</answer>
<answer id="17b2c2">`1`</answer>
<hint></hint>
<solution>
The answer is `4`.
</solution>
</activity>
```

The only important thing to know is that the `widget` attribute will change the activity to accept only one correct answer (rendering HTML radio buttons) to multiple correct answers (rendering checkboxes). The accepted values are `radio` or `checkbox` respectively. Here's an example of a `checkbox` activity:

```html
<activity id="c29c52" title="Which of the following options are true for Python" type="multiple-choice" widget="checkbox">

Select the attributes of the Python programming language.

<answer id="15ce4e" is-correct>It's interpreted</answer>
<answer id="b829c3" is-correct>It's high level</answer>
<answer id="c048ff" is-correct>It's Open Source</answer>
<answer id="46f882">It's statically compiled</answer>
<answer id="8b12c">It's low level</answer>
<answer id="17b2c2">It's closed source</answer>
<hint></hint>
<solution></solution>
</activity>
```

![](/static/github/multiple-choice-activity-mapping-code.png)

#### Code Activities

These are probably the most important and "complicated" activities. There are a lot details that can be configured for a code activity. But for now, we'll keep it simple and we'll document only a standard Jupyter activity.

```html
<activity id="1fddeb" title="Drop the column `Attack`" type="code" template="jupyter-kernel" device="jupyter">

Drop the column that defines a Pokemon's attack value in place.

<expected-outcome>
Your final dataframe should look like this:
![](images/dataframe-2.png)
</expected-outcome>
<validation-code>
assert_pd_dataframe_variable_equals_csv('df', 'solution_04.csv')
</validation-code>
<hint></hint>
<solution></solution>

<metadata name="notebook_path">Project.ipynb</metadata>
</activity>
```

You can ignore for now the attributes `type`, `template` and `device` as well as the `<metadata>` tag at the end. The only important tag for you to know is the `<validation-code>` one, which includes your assertions.

![](/static/github/code-activity-mapping-code.png)

!!!
Never use the angle brackets `<` and `>` in the markdown content. They are used here to indicate the tags.

![](/static/github/github-repo-artifacts/never-use-angle-brackets.png)
!!!