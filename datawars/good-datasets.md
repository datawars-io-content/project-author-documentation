---
order: 600
icon: database
---

# What makes a good Dataset?

A good dataset is 90% of the impact of a good project. A dataset that is interesting, engaging, of good quality is what keeps your students engaged.

The type of dataset (CSV, JSON, binary), the properties and features depends on the type of project you’re creating, so we won’t get into those details.

The key we want to focus on is the “qualitative properties” of the dataset:

* **Fun, interesting, engaging**: a dataset that teaches you something new aside from the topic you’re working on. For example, if you’re building a ML project, and using a DataSet about the impact of Nitrogen in Maize production, is something “unusual” and that most people will find interesting. Things about hobbies (music, movies, video games), engineering, science, biology will make things more interesting.
* **Good quality**: Does it have enough rows and columns? Is there variety or all the columns are the same? This collaborates with the broader picture of the project.
* **Local/close to you**: If you find datasets that are somehow closer to you, it’ll help you connect with your students. For example, [I’m from Argentina and I found a dataset](https://app.datawars.io/project/b4c63618-70e3-4233-92ad-4f12cbfbe0e8) with all the Baby names used in Argentina.
* **Domain of work**: for example, if you’re a biologist and know about some particular type of dataset that is publicly available for biology but nobody knows about it, it’ll make it more interesting.
** **Spark curiosity and potential**
  * Interesting stories (For exp, Cure the princes dataset or Livigno weather dataset, as it tells some stories behind the data)
  * Novelty: Data explores new ideas, events and areas
  * Complexity: have good relationships among variables/features.
* **Data Relevance**:
  * Alignment with Project Goals: How well does the data address the specific research question or project objective?
  * Topic Coverage: Does the data capture the key aspects and subtopics relevant to the chosen theme?

Also, it’s very useful when we combine data from different sources to create a richer dataset. For example:

* Go to the World Bank data site and find the production of rice per country. Then combine it with rainfall for all the countries. Finally, combine it with average temperatures. This would be AMAZING dataset: `Rice production and weather data in the world.CSV`
* Go to the Australian Open Data portal and find the Electricity production of each power plant in the country. Then group per city to find total electricity per city. Then, find statistics about cities in the country (like population, income, weather, etc). Finally combine everything to make a dataset: `Statistics of Australian cities 1990-2023.CSV`

### Where can you get datasets from? Ideas of public websites

It’s rather easy to find original and interesting datasets on the internet. We have done it for more than 100 projects already.
We’re asking for your help because we’re growing and need the extra help. Here’s a list of places we usually get datasets from:

* Your country’s data portal \- this is ideal to find things that are unique to you. For example, the [UK data portal](https://www.data.gov.uk/), [Ireland’s data portal](https://data.gov.ie/), or the [Argentina data portal](https://datos.gob.ar/). There’s a prevalent [list here](https://dataportals.org/).
* Subject-Specific Repositories \- these repositories are specific to our project's domain. For example, research data repositories might be available for **healthcare**, **finance**, or **education**. These can offer targeted datasets and resources relevant to our research question.
* Keyword Research \- Dataset based on list of **keywords** related to a particular subject/theme, such as (Agriculture \- Crop dataset, soil health dataset or crop disease dataset, etc. For example, [USDA NASS](https://www.nass.usda.gov/datasets/) data portal)
* Niche data portals \- things that are specific to your domain. For example, a [cyber security data website](https://www.secrepo.com/), or the climatic data [from a region in Italy](https://www.arpa.piemonte.it/).
* [https://www.pangaea.de/](https://www.pangaea.de/) \- Environmental datasets, a lot of time series and interesting climatic/chemical/biological datasets
* [World Bank Data](https://datacatalog.worldbank.org/) \- most datasets are uninteresting, but there are some gems as well
* [https://ieee-dataport.org/](https://ieee-dataport.org/) \- Interesting technical datasets. Requires a free account.
* [https://zenodo.org/search](https://zenodo.org/search) \- Mostly european and biological / climate, has good datasets.
* [https://paperswithcode.com/](https://paperswithcode.com/) \- These are usually already replicated in Kaggle, but there are exceptions from time to time
* [StackExchange](https://opendata.stackexchange.com/) & [Reddit /r/datasets](https://www.reddit.com/r/datasets/) \- Most of the time the datasets are already replicated to (or copied from) Kaggle. But there are some good gems from time to time.
* [data-is-plural.com](https://www.data-is-plural.com/): amazing weekly newsletter with access to a lot of datasets curated and explained
* [US National Park Service data](https://irma.nps.gov/Portal/): huge catalog of data associated with US National Parks
  * There’s also [an API](https://www.nps.gov/subjects/digital/nps-data-api.htm) and [a repo](https://github.com/nationalparkservice/data)
* UC Berkeley data: [https://dlab.berkeley.edu/data/uc-data](https://dlab.berkeley.edu/data/uc-data)
* Maven Analytic challenges: [https://mavenanalytics.io/challenges](https://mavenanalytics.io/challenges)
* CDC (health US) Data Catalog: [https://data.cdc.gov/browse](https://data.cdc.gov/browse)
* [https://databank.illinois.edu/](https://databank.illinois.edu/)
* [https://dhsprogram.com/](https://dhsprogram.com/)
* [https://ukdataservice.ac.uk/](https://ukdataservice.ac.uk/) ([https://internationaldata.ukdataservice.ac.uk/](https://internationaldata.ukdataservice.ac.uk/), [https://stats2.digitalresources.jisc.ac.uk/](https://stats2.digitalresources.jisc.ac.uk/))
* [https://www.societyforscience.org/research-at-home/large-data-sets/](https://www.societyforscience.org/research-at-home/large-data-sets/)

Others channels where we can find data sources:

* **Academic Publications and Research Papers:** Reviewing relevant academic papers to identify potential data sources used by researchers in a particular field.
* **Industry Reports and Datasets:** Industry reports, whitepapers, or data published by companies or organizations related to the project theme. These might offer unique insights and datasets not readily available elsewhere.
* **Recent Events and Activities:** Utilize social media listening tools to identify relevant conversations and discussions happening online. Recent events like the country election\[`US Election]`, pandemic \[`Covid Dataset`\], etc. This can lead you to new data sources or user-generated content related to your topic
* **Data Science Blogs and Communities:** Follow data science blogs, participate in online forums, and connect with other data scientists. This allows you to stay updated on new data repositories, emerging trends, and potential data sources shared by the community
* **Industry News and Publications:** Stay informed about industry news and publications related to your domain. Announcements about new data initiatives or collaborations might reveal fresh data sources

#### Dataset Quality Framework

Metrics for evaluating dataset quality. These metrics can be implemented through a scoring system or a checklist. A point system for each metric, with higher scores indicating better quality. Alternatively, a checklist can ensure all essential criteria are met for a "good" dataset.

Quality assurance and progress monitoring is implemented using spreadsheets.

1. **Volume and variety**: Dataset should contains enough rows (\~1000), features and data points
2. **Accuracy and cleanliness**: The dataset should be reliable and free from errors(no inconsistency and unnecessary columns or rows)
3. **Completeness**: Dataset with minimal missing values and outliers is preferred ( more missing values introduce biases and hinder analysis)
4. **Source Credibility:** Evaluation of the data source's reputation and reliability. ( government portal generally have high credibility than public data portals and sources)
5. **Documentation Clarity:** How well does the accompanying documentation explain the data structure, variables, and usage?
