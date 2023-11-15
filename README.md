# facts-only
## Overview
High-quality fact-checker with detailed sourcing and categorization. As of right now, this repository is not licensed and the default copyright laws apply, with owner Dennis Ramdass retaining all rights to source code and no one may reproduce, distribute, or create derivative works from this work.

## Chatbot
`facts-only` is a chatbot which prioritizes retrieval from datasets of facts that are authoratively categorized by an expert e.g. Politifact. The chatbot is designed to give clear, truthful answers within the limits of the knowledge available to it.

## Implementations

### OpenAI
#### Custom GPT (Beta)
A GPT created with the GPT creation assistant that has the GPT developer use natural language to create and configure. https://chat.openai.com/g/g-40FBMiksP-facts-only is available currently to all ChatGPT Plus subscribers.
#### Assistant (Beta)
An OpenAI assistant that is used programmatically as part of a wider system.

## Roadmap
1. Refine OpenAI GPT configuration based on user feedback
2. Move Assistant to a paid organization
3. Refine assistant configuration based on user feedback
4. Extend assistant functionality to include fetching live/recent data from factual data sources such as Politifact
5. Extend assistant functionality to include queries from different sources e.g. Is tweet X factual?
6. Extend assistant functionality to include multi-modal input e.g. audio or video of political debate
7. Non-OpenAI implementations with a goal to keep a single abstraction layer using popular frameworks e.g. LangChain, Haystack
