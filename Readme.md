# Credit Default Model Template
This template is to be used as the starting point for all credit scoring and credit default models.  It includes the following:
- Domino Environment with approved libraries and configurations
- Approved Domino Data Sources for Credit scoring
- Model Development Tasks/Goals
- Project file structure
- Sample Notebooks, Training, and Application Scripts.
- Recommended Hardware Tier
- Starting Tags

## Project File Structure Structure
- admin
- apps
- documentation
- models
- results
- scripts
- visualizations

## Domino Environment Definition
[Domino Environment](R115374714469.dkr.ecr.us-west-2.amazonaws.com/cloud-sedemo/environment:6760751fa89a19743d395951-5
FROM)
```
quay.io/domino/domino-standard-environment:ubuntu22-py3.10-r4.4-domino6.0-standard
```
DOCKER INSTRUCTIONS
```
USER root
RUN pip install --upgrade pandas seaborn
RUN pip install h2o streamlit eli5
USER ubuntu
```
PLUGABLE IDEs
```
jupyter:
  title: "Jupyter (Python, R, Julia)"
  iconUrl: "/assets/images/workspace-logos/Jupyter.svg"
  start: [ "/opt/domino/workspaces/jupyter/start" ]
  supportedFileExtensions: [ ".ipynb" ]
  httpProxy:
    port: 8888
    rewrite: false
    internalPath: "/{{ownerUsername}}/{{projectName}}/{{sessionPathComponent}}/{{runId}}/{{#if pathToOpen}}tree/{{pathToOpen}}{{/if}}"
    requireSubdomain: false
jupyterlab:
  title: "JupyterLab"
  iconUrl: "/assets/images/workspace-logos/jupyterlab.svg"
  start: [  "/opt/domino/workspaces/jupyterlab/start" ]
  httpProxy:
    internalPath: "/{{ownerUsername}}/{{projectName}}/{{sessionPathComponent}}/{{runId}}/{{#if pathToOpen}}tree/{{pathToOpen}}{{/if}}"
    port: 8888
    rewrite: false
    requireSubdomain: false
vscode:
  title: "vscode"
  iconUrl: "/assets/images/workspace-logos/vscode.svg"
  start: [ "/opt/domino/workspaces/vscode/start" ]
  httpProxy:
    port: 8888
    requireSubdomain: false
rstudio:
  title: "RStudio"
  iconUrl: "/assets/images/workspace-logos/Rstudio.svg"
  start: [ "/opt/domino/workspaces/rstudio/start" ]
  httpProxy:
    port: 8888
    requireSubdomain: false
```







#### In this workshop, you will work through an end-to-end workflow broken into various labs to -

* Read in data from a live datasource
* Prepare your data in an IDE of your choice, with an option to leverage distributed computing clusters
* Train several models in various frameworks
* Compare model performance across different frameworks and select the best-performing model
* Deploy model to a containerized endpoint and web-app frontend for consumption
* Leverage collaboration and documentation capabilities to make all work reproducible and sharable!  
  
You will find a full walkthrough of our Workshop here: [VERSION 6.x WORKSHOP LINK](https://docs.google.com/document/u/4/d/11eA3ney10KzX7GF9G7f5n72f4p7k7CHSpLxoUfbAGE8/pub)

You will find a full walkthrough of our Workshop here: [VERSION 5.x WORKSHOP LINK](https://docs.google.com/document/d/e/2PACX-1vS9LKbBYYOrsDmshmKvEIUkDMYVMAivoodg1CTEgjZRPW_IJFV2Un4l5uaE2jI1BsbN3-tQ8IMSkGoL/pub)
