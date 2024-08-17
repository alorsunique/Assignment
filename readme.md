# Repository Overview

This repository contains two main folders:

## 1. LibreChat Modified Files

This folder includes all the files that I have modified from [danny-avila's GitHub repository](https://github.com/danny-avila/LibreChat). I have added a `.env` file derived from the example provided in the original project, as it is required to run a local copy of the project.

To integrate Azure OpenAI, I followed the instructions from their official documentation. Since Azure OpenAI differs from regular OpenAI, as they use different API keys, I followed their guidelines on adding custom AI endpoints. This process required the creation of a `docker-compose.override.yml` file.

With this file created, it is now possible to use custom AI endpoints. I then followed their documentation on adding Azure OpenAI. To do this, I added the `librechat.yaml` file derived from the example file they provided. Inside, I included the sample code provided in their documentation. I removed all other models except for GPT-3.5, as it was the only model I had deployed in Azure OpenAI. I selected this model to be conservative with the free credits provided upon registration, in case they are needed for future tasks.

In the `librechat.yaml` file included in this project, I have replaced my group, API key, and instance with placeholders.

## 2. Azure Function Document Intelligence

This folder contains the `function_app.py` file, where I coded the API, along with the `requirements.txt` file, so that Azure can source the appropriate packages for the function to run.

The `function_app.py` file contains the code for the function. To create it, I combined sample code from examples provided by Azure for both Azure Functions and Azure Document Intelligence. Currently, it can take in a URL of PDF files by adding it as a parameter in the link. For the output, I was able to get Azure Document Intelligence to read PDF files and return the results. I chose to display the content of the `poller.result`, similar to how content is displayed in the content tab on the Document Intelligence Studio website. Following the initial content, I display the entire `poller.result`, which I have converted into a dictionary that can be written to a JSON file.

# Sample of Results

For LibreChat, I have included a screenshot of my conversation with the chatbot last night. I have also included a screenshot of the metrics that can be seen on my deployed model in Azure.

![LibreChat Conversation Screenshot]("Images/Conversation.png")
![LibreChat Metrics Screenshot]("Images/Metrics.png")

For Document Intelligence, I have included a screenshot of a sample PDF file and the result of calling the function with the URL of the said PDF.

![Sample PDF Screenshot]("Images/Source.png")
![Document Intelligence Function Result Screenshot]("Images/PDF Result.png")

Here is a [link](https://alorsfunctiontest2.azurewebsites.net/api/alors_http_trigger?code=aYWCvnbbA5fN60VxqvZ_usUqlxXBVYp52Dofp5ubNNF_AzFueUtt0A%3D%3D) to the Function url.

---

Thank you for taking the time to view this repository. I hope to discuss my output and thought process with you if possible.
