---
sidebar_position: 1
---

# Tutorial: deploy the KOS Kit Explorer as a statically-generated GitHub Pages site

This tutorial will guide you in deploying the KOS Kit Explorer as a statically-generated site using GitHub Actions and GitHub Pages.

You should only use static site generation for relatively small datasets (thousands of concepts).

### Create and configure a GitHub repository

#### Copy the template GitHub repository

Follow [these instructions](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template) on creating a GitHub repository from a template, using [this template repository](https://github.com/kos-kit/hasset-explorer).

#### Configure GitHub Pages

Follow [these instructions](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow) on publishing GitHub Pages with a custom GitHub Actions workflow.

### Replace `data.nt` in your repository with your SKOS taxonomy

Your taxonomy can serialized be in any RDF format supported by [N3.js](https://github.com/rdfjs/N3.js):

- [N-Quads](https://www.w3.org/TR/n-quads/)
- [N-Triples](https://www.w3.org/TR/n-triples/)
- [Notation3 (N3)](https://www.w3.org/TeamSubmission/n3/)
- [Turtle](https://www.w3.org/TR/turtle/)
- [TriG](https://www.w3.org/TR/trig/)

### Generate the site

The site will be regenerated whenever you push commits to the repository.

You can also manually generate the site by [manually running the GitHub Actions workflow](https://docs.github.com/en/actions/using-workflows/manually-running-a-workflow). The name of the workflow is "Continuous Deployment".
