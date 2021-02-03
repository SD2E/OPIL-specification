# OPIL-specification

This repository contains the master specification document for the Open Protocol Interface Language (OPIL) data model, formatted in LaTeX.  The workflow for updating the specification is to clone, edit, and submit a pull request on the main branch.

Use the issue tracker to flag problems with the existing specification and review ongoing issues under consideration.

## Submitting changes to the specification

Before writing text for a non-trivial change, please have it approved by discussion as an Issue.

Proposed changes should be made in either a branch or a separate fork on GitHub.  To do this, follow standard git branching or forking procedure.

When you are ready for your changes to be reviewed for incorporation, create a pull request.
If you need help on pull requests see: https://help.github.com/articles/about-pull-requests/

## Using LaTeX

### Building the PDF from LateX

To build, run these commands and check the output for errors. If there are errors, resolve them and re-run the failed build step before proceeding.

    pdflatex opil
    bibtex opil
    pdflatex opil
    pdflatex opil

Note that pdflatex is run several times. Each successive pass mows down unresolved references from the previous passes. For example, the extra pdflatex commands set references correctly after bibtex completes. You don’t need to do this in every build unless the bibliography has changed.  For development purposes, you may just need to run pdflatex once.



