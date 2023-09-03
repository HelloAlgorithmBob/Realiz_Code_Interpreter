# Code Interpreter API

A LangChain implementation of the ChatGPT Code Interpreter.
Using CodeBoxes as backend for sandboxed python code execution.
[CodeBox](https://github.com/shroominic/codebox-api/tree/main) is the simplest cloud infrastructure for your LLM Apps.
You can run everything local except the LLM using your own OpenAI API Key. (It is noted that I create this project based on [This original project](https://github.com/shroominic/codeinterpreter-api))

## Features

- Dataset Analysis, Stock Charting, Image Manipulation, ....
- Internet access and auto Python package installation
- Input `text + files` -> Receive `text + files`
- Conversation Memory: respond based on previous inputs
- Run everything local except the OpenAI API

## Installation

Get your OpenAI API Key [here](https://platform.openai.com/account/api-keys) and install the package.

```bash
pip install "codeinterpreterapi[all]"
```

Everything for local experiments are installed with the `all` extra.
For deployments, you can use `pip install codeinterpreterapi` instead which does not install the additional dependencies.

## Usage

To configure OpenAI and Azure OpenAI, ensure that you set the appropriate environment variables (or use a .env file):

For OpenAI, set the OPENAI_API_KEY environment variable:
```
export OPENAI_API_KEY=your_openai_api_key
```

For Azure OpenAI, set the following environment variables:
```
export OPENAI_API_TYPE=azure
export OPENAI_API_VERSION=your_api_version
export OPENAI_API_BASE=your_api_base
export OPENAI_API_KEY=your_azure_openai_api_key
export DEPLOYMENT_NAME=your_deployment_name
```

Remember to replace the placeholders with your actual API keys and other required information.

## Several Examples (You can find codes in /examples and support file in /examples/assets)

### You can add these lines in the code to set up your environment variables

```python
import os
# Set up your environment variables
os.environ['OPENAI_API_KEY'] = 'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX'
openai_api_key = os.environ['OPENAI_API_KEY']
```

## Streamlit WebApp

To start the web application created with streamlit:

```bash
streamlit run app.py
```

It is noted that you would better add several lines to set up your environment variables before running "app.py"