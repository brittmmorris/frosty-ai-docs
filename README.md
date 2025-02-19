# Frosty AI Documentation

## Table of Contents

1. [Introduction](#introduction)
2. [Frosty AI Vocab](#frosty-ai-vocab)
   - [Organization](#organization)
   - [Workspaces](#workspaces)
   - [Routers](#routers)
     - [Multiple Routers in a Workspace](#multiple-routers-in-a-workspace)
   - [Providers](#providers)
3. [Quick Start Guide](#quick-start-guide)
   - [1. Sign Up](#1-sign-up)
   - [2. Create Workspaces](#2-create-workspaces)
   - [3. Set Up Routers](#3-set-up-routers)
   - [4. Test in the UI](#4-test-in-the-ui)
   - [5. Integrate Frosty AI in Your Code](#5-integrate-frosty-ai-in-your-code)
   - [6. Manage & Analyze](#6-manage--analyze)
4. [Resources](#resources)

## Introduction

**Frosty AI** empowers teams to manage, optimize, and scale AI operations effortlessly with multi-LLM routing, advanced analytics, and AI-driven insights—all in one platform. 

With Frosty AI, you can:

- **LLM Routing Interface:** Easily connect, configure, and switch between different LLMs using a web-based UI.
- **Prompt Management:** Centrally manage your prompts, including versioning and tracking, to maintain consistency and efficiency. (Coming Soon)
- **Analytics Dashboard:** Log and visualize interactions, success rates, and other key metrics to gain insights into your AI operations.
- **AI Recommendations:** Leverage AI-driven insights to improve your prompts and overall system performance. (Coming Soon)
- **Continuous Updates:** Our team continuously adds and updates supported providers and models to keep you ahead in AI innovation.

## Frosty AI Terms

### Organization

The top-level entity that a company or enterprise creates when they sign up for Frosty AI. This is where all company-wide settings and management take place.

### Workspaces

Sub-divisions within an Organization, tailored for different departments, teams, or projects. Workspaces serve as isolated environments where specific groups can manage their LLM interactions, analytics, and configurations.

### Routers

The core feature within a Workspace. **Routers** are responsible for directing requests to different LLM providers. They allow users to configure which LLM to use and manage the flow of information without altering the underlying code.

#### Multiple Routers in a Workspace

In a single Workspace, you can create multiple Routers. This is particularly useful when your team or project needs to interact with different LLMs for various tasks. For example:

- **Task-Specific Routing:** You might have one Router dedicated to handling customer support queries using a conversational LLM, while another Router is optimized for generating technical documentation using a different, more specialized LLM.
  
- **A/B Testing:** You can set up multiple Routers to perform A/B testing between different LLM providers or configurations. This allows you to compare performance, response quality, and cost-effectiveness across different models, helping you make informed decisions on which LLM best suits your needs.

- **Redundancy and Failover:** Having multiple Routers also provides redundancy. If one LLM provider experiences downtime, you can quickly switch to another Router connected to a different provider, ensuring continuous operation without any interruptions.

By leveraging multiple Routers, you can maximize flexibility, optimize performance, and ensure that your AI-driven workflows are robust and efficient.

### Providers

The various LLMs that can be connected and switched between through Routers. These could include services like OpenAI, Anthropic, Meta, MistralAI, and more coming soon with the flexibility to bring your own model (coming soon).

## Quick Start Guide

### 1. Sign Up

A company signs up for Frosty AI and creates an **Organization**.

### 2. Create Workspaces

Within the Organization, different teams (e.g., marketing, R&D) create their own **Workspaces**.

### 3. Set Up Routers

In each Workspace, teams set up **Routers** to connect to various **Providers** depending on their specific needs.

### 4. Test in the UI

If you don't want to set Frosty AI up in your code just yet, you can explore and experiment directly in the UI. Navigate to the **Router** page to compare different models and prompts to see what works best for your use case. Alternatively, head over to the **Testing** page to compare more than one model at a time, allowing you to make informed decisions before integrating into your codebase.

### 5. Integrate Frosty AI in Your Code
To start using Frosty AI in your Python project, follow the example below:

#### Install the Frosty AI SDK
Before integrating Frosty AI into your project, install the SDK using pip:

```bash
pip install frosty-ai
```

```python
# Import Frosty SDK
from frosty_ai import Frosty

def main():
    router_id = "[YOUR_ROUTER_ID]"
    router_key = "[YOUR_ROUTER_KEY]"

    try:
        # Create an instance of the Frosty class
        frosty_sdk = Frosty(router_id, router_key)

        # Make a text generation request
        chat_result = frosty_sdk.chat([{
            "role": "user", 
            "content": "tell me a 10-word joke about the weather"
        }])

        # Make an embeddings generation request
        embeddings_result = frosty_sdk.embeddings([
            "Embed this sentence.", 
            "As well as this one."
        ])

        print(f"Text generation result: {chat_result}")
        print(f"Embeddings generation result: {embeddings_result}")

    except Exception as e:
        print(f"An error occurred: {e}")

if __name__ == "__main__":
    main()
```

### 6. Manage & Analyze

Teams can analyze responses, and switch LLM providers seamlessly within their Workspace. Frosty AI’s analytics dashboard provides insights into prompt performance, success rates, and other key metrics, enabling continuous optimization and improvement.

## Resources

- [Frosty AI PyPI Package](https://pypi.org/project/frosty-ai/)
- [Demos and Tutorials](#)
- [Support](https://github.com/brittmmorris/frosty-ai-docs/issues)
