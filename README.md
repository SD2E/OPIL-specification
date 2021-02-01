# SBOL-specification

This repository contains the master specification document for the Open Protocol Interface Language (OPIL) data model, formatted in LaTeX.  The workflow for updating the specification is to clone, edit, and submit a pull request on the master.

Members of the SD2E community may use the issue tracker to flag problems with the existing specification and review ongoing issues under consideration.

## Submitting changes to the specification

Before writing text for a non-trivial change, please have it approved by discussion as an Issue.

Proposed changes should be marked with the appropriate version
macros. The LaTeX command `\threezeroone` has been provided for this
purpose. See examples in the LaTeX source for proper usage.

Proposed changes should be made in either a branch or a separate fork on GitHub.  To do this, follow standard git branching or forking procedure.

Here is an example of git commands to achieve this:

```shell
git clone https://github.com/SynBioDex/SBOL-specification.git
cd SBOL-specification

# Make sure no one has made anymore changes
git pull origin master
# Create new branch
git checkout -b <newBranch>

# Make your edits
git add <filesYouChanged>
git commit
git push origin <newBranch>
```

When you are ready for your changes to be reviewed for incorporation, create a pull request.
If you need help on pull requests see: https://help.github.com/articles/about-pull-requests/

## Automation

This repository uses a [Github Action](https://github.com/features/actions) to automatically build the project when a pull request is made to the `master` branch, or a push is made to the branch (inlcuding when a PR is merged).
This creates a PDF and uploads it as as a [workflow artefact](https://help.github.com/en/actions/configuring-and-managing-workflows/persisting-workflow-data-using-artifacts); GitHub retains these for 90 days.
You can download this PDF by clicking on the green check mark beside a commit, then clicking 'details' in the popover; this will navigate to a different page, where you can click on 'Artefacts' and then 'PDF'.

If building the PDF fails, then this is shown by a red cross. 
This does not necessarily mean that there is a problem with the specification document: automated builds will also fail if they are for a pull request that has already been closed, or are from a different repository (i.e., a fork rather than a branch). 

The action is defined by the file [`.github/workflows/main.yml`](./.github/workflows/main.yml)

## Using LaTeX

### Building the PDF from LateX

To build, run these commands and check the output for errors. If there are errors, resolve them and re-run the failed build step before proceeding.

    pdflatex sbol3
    bibtex sbol3
    pdflatex sbol3
    pdflatex sbol3

Note that pdflatex is run several times. Each successive pass mows down unresolved references from the previous passes. For example, the extra pdflatex commands set references correctly after bibtex completes. You don’t need to do this in every build unless the bibliography has changed.  For development purposes, you may just need to run pdflatex once.



