# Sharing data

Publishing research data is an important step in ensuring that your research outputs are following
the [**F**indable **A**ccessible **I**nteroperable **R**eusable (FAIR) principles](https://www.go-fair.org/fair-principles/)
for scientific data management. 
Although making your work accessible to others involves costs (effort and time, mostly), it 
[considerably increases the reach of your work](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0230416) 
and thus also benefits your academic career.
You can make the process of sharing your work, data, and code substantially easier
if you [plan it right from the start of your project](https://the-turing-way.netlify.app/project-design/project-design.html).
A data management plan,
good organization of your data,
and good documentation of your actions
will all help make this process much easier,
and are also essential for you to be able to reproduce and understand your own work.
In practice, your closest collaborator is often you from 6 months ago!

```{admonition} How to read this document
:class: tip

This document is organized around a series of questions that you can ask yourself when planning to share data.
For each question, 
we provide you with good external resources that provide answers. 
```


## Check data sharing constraints 
Your first step should be to ensure that you **can** in fact share the raw or derivative data you intend to share. 
Here are some reasons you may be constrained in your ability to share your data. 
Most of the time this **does not mean that you cannot share any data**!
Often it just means that someone has already made a decision on **how** you should share data.

Here are some scenarios that could suggest that there are constraints on how you share data:

- there is already a [**data management plan**](https://the-turing-way.netlify.app/reproducible-research/rdm/rdm-dmp.html)
that describes 
how work derived from a dataset or project are going to be shared.
If a data management plan exists,
you should follow it!
- the data you are working on involves **human participants**. 
You are responsible to ensure that the privacy of your participants is protected and 
identifiable information is not shared.
- you are reusing data that someone else has acquired. 
These data may have a **license or data usage agreement** that you have agreed to and that you may be bound by. 

```{note}
Data management plans are increasingly becoming a requirement by funding agencies and if your group. 
If your group needs advice on this, you can reach out to the DNP or the Douglas Open Science group. 
```
 
These are questions your principal investigator, lab manager, 
or someone responsible for data curation in your group may be able to help answer.

```{TODO}
Add footnotes for:
- de-identification, 
- licensing, and 
- data management plans.

Get persistent links for resources from providers (if possible)
```

```{admonition} Additional resources for data sharing constraints
:class: tip
- [Tri-Council policy on privacy and confidentiality](https://ethics.gc.ca/eng/tcps2-eptc2_2018_chapter5-chapitre5.html)
- [Slides by McGill on data sharing constraint considerations](https://frq.gouv.qc.ca/app/uploads/2021/07/factors-to-consider-to-inform-decision_v14.pdf)
```

## What is the purpose for sharing the data

All shared data should be well documented, 
well organized, 
and follow community accepted data standards and file formats.
But depending on the main purpose for sharing data, 
you may make different decisions on how and what to share. 
Generally, 
there are two options:

1. You are sharing __a dataset__ that you have acquired (e.g. raw data) or that you have processed (derived data).
Your goal here is that someone else might want to find these data useful, will reuse them and give you credit for your work.
2. You are sharing __data as part of an empirical manuscript submission__. 
Your goal here is to support your findings and figures with the data that support your analyses - 
and possibly to fulfill the requirements of the journal.

The main difference between these two options is that option 2. is a special case of 1. 
That is, to share data in support of a publication, 
you should follow the same steps and rigour in sharing a standalone dataset
but you will also want to consider providing your data in a way 
that facilitates reproduction of the analyses described in your publication.

### Sharing a dataset for re-use
```{admonition} Consider turning your shared dataset into a publication
:class: tip

All shared data should have a DOI and be citable.
But there are also dedicated data journals that will allow you to make an in depth description of your data
and clearly show your contribution.
[Here is an overview of some data sharing journals](https://www.fosteropenscience.eu/foster-taxonomy/open-data-journals).

```
This is a major scientific contribution that stands on its own.
The main goal here is to provide your data in as standardized a form and
with as detailed a description as possible.

To prepare your data for sharing, you should:
- provide a detailed explanation of the data in a README file.
  - Include information on acquisition, processing, inclusion, and exclusion criteria
  - [Turing way documentation guidelines](https://the-turing-way.netlify.app/reproducible-research/rdm/rdm-metadata.html)
  - [How to make data accessible](https://www.software.ac.uk/how-can-you-make-research-data-accessible)
- For derivative data, include a reference to the raw data detailed descriptions of any processing you have done
  - Provide a reference to the raw data that your dataset is derived from (publication, DOI, or URL)
  - you should include the exact sequence of processing commands that were performed
  - ideally this would be in the form of the actual script files you have run
- data files should follow community accepted standards for file formats and naming 
  - e.g. [BIDS](https://bids-specification.readthedocs.io/en/stable/) for imaging data
  - where no standards exist or are applicable, 
  make sure that file names are standardized, human readable, and explained in the README file
  - make sure that data files are organized in a hierarchical directory structure with human readable directory names.
  the directories should be referred to in the README with a brief explanation of their contents
- Share tabular data in a standardized and human readable way
  - Don't mix tabular and non-tabular data (i.e. don't include images or text annotations in an excel spreadsheet)
  - Use common data formats, ideally text based ones like `.csv` (comma separated files) or `.tsv` (tab separated files)
  - Provide the name of variables in the first row of a table (header row)
  - Use human readable variable names (and explain them in data dictionaries)
  - [Turing way guidelines on tabular data](https://the-turing-way.netlify.app/reproducible-research/rdm/rdm-spreadsheets.html)
- Provide explanations for all variables used, e.g. with data dictionaries
  - data dictionaries are tables that map each variable name to a human readable definition and also provide
  additional information on things like allowable values, range of values, unit types.
  - data dictionaries are very helpful for re-users of your data!
  - [OSF tutorial on how to create data dictionaries](https://help.osf.io/hc/en-us/articles/360019739054-How-to-Make-a-Data-Dictionary)

### Sharing data in support of a published manuscript

Let's assume you have just finished the manuscript for an exciting research project (✨ congrats ✨)
and now you want to share the data that support your central findings and figures together
with the manuscript.
This is not only a great way to ensure that other can follow and re-use your research 
that will make it more likely your work will have an impact, 
many journals are starting to require the sharing of data with publication.

```{admonition} Consider sharing derivative data on their own
:class: tip
If your analyses are based on data that you have derived (e.g. through preprocessing with an image processing pipeline)
from an existing dataset,
then you should consider to share these derived data as a standalone dataset.
You can then refer to the shared derived data in your publication and your publication specific data sharing. 
```

Preparing data to be shared in support of your analyses should follow the same general principles
as when you are {ref}`sharing a dataset for re-use<research_methods/sharing_data:Sharing a dataset for re-use>`.
In contrast to sharing a standalone dataset, 
the focus here is more on facilitating a reader in reproducing and understanding the specific analyses
you have described in your publication. 

```{admonition} Consider sharing code with data
:class: note
Sharing data even with the best annotations and descriptions
is not as easy to understand and reproduce as when you also
share your analysis code. 
See this [great overview of "The Turing Way"](https://the-turing-way.netlify.app/reproducible-research/reproducible-research.html)
```

Here are some questions to get you started

- What analyses should your readers be able to reproduce and have access to?
  - all major figures
  - the central claims of the publication
  - specific pre-processing, inclusion or exclusion steps
  - outlier analyses
  - etc
- What are the steps taken between your raw data and the major outcomes you want to show your readers
  - Here it can be helpful to look at your methods figure
  - Alternatively, draw a flow chart on a piece of paper or write it down as hierarchical text
  - If you do share code with your paper, each step should ideally map to a specific command or script
  - For each step, make a note of the input and output data required
- What intermediate data do you want to share?
  - Some analyses steps take too long, results are too large, 
  or require too many resources for a reader to reasonably re-run them
  - Other times, raw data may not be possible to share due to privacy concerns, 
  whereas derivative summary data may be uncomplicated
  - In these cases it may make sense to just share intermediate data
  - Here the flow-chart will come in very handy to inform you on what data are needed to reproduce a given analysis step
- Make a data sharing plan
  - Based on the previous decisions and information, you should now make a plan on what to share and how
  - Start a text document and write down each data file you want to share and what name you plan to give it and in what 
  directory you plan to store it
  - This can become the foundation for your README file and your data dictionaries
  - This plan will also help you make sure that you are using file names consistently, e.g. across your README file,
  in your data availability statement, and in your scripts
- Can my readers understand the intermediate data files
  - Make sure that intermediate data also have human readable names
  - They should also be described in the documentation of your shared data
- Do the data really work with my analysis code or descriptions
  - Once you have all of this, you should review it
  - If you have code to be shared with the publication and data, make sure it runs and produces the expected outcomes
  - Go over your data sharing plan with a colleague to check if it makes sense or things are missing
  - Ask someone to review the documents to see if they can follow your analyses given the data and documentation

At the end of this process, 
you should have a directory with description files (README, data dictionaries) and data
that you want to share.

## What repository should the data be shared on

Once you are clear on what data you want to share and for what purpose,
you can make a decision on the data publishing repository you want to use. 
A data repository primarily serves two purposes:

- to provide the storage space for your data to be hosted (so you don't have to pay for or worry about it)
- mint a **D**igital**O**bject**I**dentifier for your dataset, 
a permanent record and link that will forever point to your dataset and that others can use to access your data.
This is often also required by journals for data accessibility requirements.

```{TODO}
Say more things about ways to choose and differences in scope of platforms
```

The Nature Publishing Group maintains a repository of recommended 
[subfield specific](https://www.nature.com/sdata/policies/repositories) and 
[domain general data repositories](https://www.nature.com/sdata/policies/repositories#general) that you can take a look at.

Another great resource is the 
[data publishing guideline of the F1000 publishing platform](https://f1000research.com/for-authors/data-guidelines).

A good domain general data repository is [Zenodo.org](https://zenodo.org/). 
Zenodo is funded by the [CERN](https://home.cern/), 
and apart from points for coolness this also means a high level of confidence that it will remain accessible long into the future.
We can recommend Zenodo for basic data sharing needs.

Another great platform for data sharing is the [**O**pen**S**cience**F**ramework](https://osf.io/). 
This is maintained by the [Center for Open Science](https://www.cos.io/about/mission)

Often these data repositories allow you to generate a DOI before you publish your data.
This can be very helpful if you want to include the DOI in your manuscript submission,
but also still want to make changes to the data you intend to share.

## What license to share data with
Generally you should share your data with as open and permissive a license as you can. 
A good starting point are the Creative Common Licenses, 
e.g. [CC BY 4](https://creativecommons.org/licenses/by/4.0/?ref=chooser-v1).
You can make choices on permissions for commercial use, how data users should cite you and so on. 
Here is a [Creative Commons License selector tool](https://chooser-beta.creativecommons.org/).

There may also be constraints on the type of license you can choose.
- your data may be based on data that already came with a license and you may be bound to re-share under the same terms
- your group, or the project you work on may have a data management plan that specifies a license
- your data repository may require that you use a certain type of license
- the journal you are publishing to may require a certain license

These are good things to check with your PI or lab manager.

```{admonition} Additional resources for selecting a license
:class: tip
- [Turing Way data licenses](https://the-turing-way.netlify.app/reproducible-research/licensing/licensing-data.html)
- [Guide to Open Data Licensing](http://opendefinition.org/guide/data/)
- [OSF guide on licenses](https://help.osf.io/hc/en-us/articles/360019739014-Licensing)
```

## Additional resources
- [OSF guidelines](https://help.osf.io/hc/en-us)
- [The Turing Way](https://the-turing-way.netlify.app/welcome.html)
- [Data sharing resources of the McGill library](https://www.mcgill.ca/library/services/data-services/sharing)