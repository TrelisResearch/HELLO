Title: Initial setup - Anthropic

URL Source: http://docs.anthropic.com/en/docs/initial-setup

Markdown Content:
Initial setup - Anthropic
===============
  

   

[Anthropic home page![Image 3: light logo](https://mintlify.s3.us-west-1.amazonaws.com/anthropic/logo/light.svg)![Image 4: dark logo](https://mintlify.s3.us-west-1.amazonaws.com/anthropic/logo/dark.svg)](http://docs.anthropic.com/)

English

Search...

*   [Go to claude.ai](https://claude.ai/)
*   [Research](https://www.anthropic.com/research)
*   [News](https://www.anthropic.com/news)
*   [Go to claude.ai](https://claude.ai/)

Search...

Navigation

Get started

Initial setup

[Welcome](http://docs.anthropic.com/en/home)[User Guides](http://docs.anthropic.com/en/docs/welcome)[API Reference](http://docs.anthropic.com/en/api/getting-started)[Prompt Library](http://docs.anthropic.com/en/prompt-library/library)[Release Notes](http://docs.anthropic.com/en/release-notes/overview)[Developer Newsletter](http://docs.anthropic.com/en/developer-newsletter/overview)

*   [Developer Console](https://console.anthropic.com/)
*   [Developer Discord](https://www.anthropic.com/discord)
*   [Support](https://support.anthropic.com/)

##### Get started

*   [Overview](http://docs.anthropic.com/en/docs/welcome)
*   [Initial setup](http://docs.anthropic.com/en/docs/initial-setup)
*   [Intro to Claude](http://docs.anthropic.com/en/docs/intro-to-claude)

##### Learn about Claude

*   Use cases
    
*   [Models](http://docs.anthropic.com/en/docs/about-claude/models)
*   [Security and compliance](https://trust.anthropic.com/)

##### Build with Claude

*   [Define success criteria](http://docs.anthropic.com/en/docs/build-with-claude/define-success)
*   [Develop test cases](http://docs.anthropic.com/en/docs/build-with-claude/develop-tests)
*   Prompt engineering
    
*   [Text generation](http://docs.anthropic.com/en/docs/build-with-claude/text-generation)
*   [Embeddings](http://docs.anthropic.com/en/docs/build-with-claude/embeddings)
*   [Google Sheets add-on](http://docs.anthropic.com/en/docs/build-with-claude/claude-for-sheets)
*   [Vision](http://docs.anthropic.com/en/docs/build-with-claude/vision)
*   [Tool use (function calling)](http://docs.anthropic.com/en/docs/build-with-claude/tool-use)
*   [Computer use (beta)](http://docs.anthropic.com/en/docs/build-with-claude/computer-use)
*   [Prompt caching (beta)](http://docs.anthropic.com/en/docs/build-with-claude/prompt-caching)
*   [Message Batches (beta)](http://docs.anthropic.com/en/docs/build-with-claude/message-batches)
*   [PDF support (beta)](http://docs.anthropic.com/en/docs/build-with-claude/pdf-support)
*   [Token counting (beta)](http://docs.anthropic.com/en/docs/build-with-claude/token-counting)

##### Test and evaluate

*   Strengthen guardrails
    
*   [Using the Evaluation Tool](http://docs.anthropic.com/en/docs/test-and-evaluate/eval-tool)

##### Administration

*   [Admin API](http://docs.anthropic.com/en/docs/administration/administration-api)

##### Resources

*   [Glossary](http://docs.anthropic.com/en/docs/resources/glossary)
*   [Model Deprecations](http://docs.anthropic.com/en/docs/resources/model-deprecations)
*   [System status](https://status.anthropic.com/)
*   [Claude 3 model card](https://assets.anthropic.com/m/61e7d27f8c8f5919/original/Claude-3-Model-Card.pdf)
*   [Anthropic Cookbook](https://github.com/anthropics/anthropic-cookbook)
*   [Anthropic Courses](https://github.com/anthropics/courses)

##### Legal center

*   [Anthropic Privacy Policy](https://www.anthropic.com/legal/privacy)

Get started

Initial setup
=============

Let’s learn how to use the Anthropic API to build with Claude.

In this example, we’ll have Claude write a Python function that checks if a string is a palindrome.

[​](http://docs.anthropic.com/en/docs/initial-setup#prerequisites)

Prerequisites
-----------------------------------------------------------------------------------

You will need:

*   An Anthropic [Console account](http://docs.anthropic.com/en/docs/console.anthropic.com)
*   An [API key](https://console.anthropic.com/settings/keys)
*   Python 3.7+ or TypeScript 4.5+

Anthropic provides [Python and TypeScript SDKs](https://docs.anthropic.com/en/api/client-sdks), although you can make direct HTTP requests to the API.

[​](http://docs.anthropic.com/en/docs/initial-setup#start-with-the-workbench)

Start with the Workbench
---------------------------------------------------------------------------------------------------------

Any API call you make–-regardless of the specific task-–sends a well-configured prompt to the Anthropic API. As you’re learning to make the most of Claude, we recommend that you start the development process in the Workbench, a web-based interface to Claude.

Log into the [Anthropic Console](https://console.anthropic.com/) and click **Workbench**.

In the middle section, under User, let’s ask Claude a question.

User

```Unset
Why is the ocean salty?
```

Click **Run**. On the right side, you’ll see output like

Response

```Unset
The ocean is salty due to several factors:

1. Weathering of rocks: Over millions of years, rain, rivers, and streams have eroded rocks containing mineral salts. These salts are carried into the ocean by water runoff.
2. Volcanic activity: Underwater volcanoes and hydrothermal vents release minerals, including salts, into the ocean water.
3. Atmospheric deposition: Salt particles from ocean spray can be carried by wind and deposited back into the ocean.
4. Evaporation: As water evaporates from the surface of the ocean, it leaves behind dissolved salts, increasing the concentration of salt in the remaining water.
5. Biological processes: Some marine organisms contribute to the ocean's salinity by releasing salt compounds as byproducts of their metabolism.

Over time, these processes have continuously added salts to the ocean, while evaporation removes pure water, leading to the ocean's current salinity levels. It's important to note that the total amount of salt in the ocean remains relatively stable because the input of salts is balanced by the removal of salts through processes like the formation of evaporite deposits.
```

This is a good answer, but let’s say we wanted to control the exact type of answer Claude gives. For example, only allowing Claude to respond to questions with poems. We can control the format, tone, and personality of the response by adding a System Prompt.

System prompt

```Unset
You are a world-class poet. Respond only with short poems.
```

Click **Run** again.

Response

```Unset
The ocean's salty brine,
A tale of time and elements combined.
Rocks and rain, a slow erosion,
Minerals carried in solution.
Eons pass, the salt remains,
In the vast, eternal watery domain.
```

See how Claude’s response has changed? LLMs respond well to clear and direct instructions. You can put the role instructions in either the system prompt or the user message. We recommend testing to see which way yields the best results for your use case.

Once you’ve tweaked the inputs such that you’re pleased with the output–-and have a good sense how to use Claude–-convert your Workbench into an integration.

Click **Get Code** to copy the generated code representing your Workbench session.

[​](http://docs.anthropic.com/en/docs/initial-setup#install-the-sdk)

Install the SDK
---------------------------------------------------------------------------------------

Anthropic provides SDKs for Python (3.7+) and TypeScript (4.5+).

*   Python
*   TypeScript

In your project directory, create a virtual environment.

Python

```python
python -m venv claude-env
```

Activate the virtual environment using

*   On macOS or Linux, `source claude-env/bin/activate`
*   On Windows, `claude-env\Scripts\activate`

Python

```python
pip install anthropic
```

[​](http://docs.anthropic.com/en/docs/initial-setup#set-your-api-key)

Set your API key
-----------------------------------------------------------------------------------------

Every API call requires a valid API key. The SDKs are designed to pull the API key from an environmental variable `ANTHROPIC_API_KEY`. You can also supply the key to the Anthropic client when initializing it.

*   macOS and Linux
*   Windows

```bash
export ANTHROPIC_API_KEY='your-api-key-here'
```

[​](http://docs.anthropic.com/en/docs/initial-setup#call-the-api)

Call the API
---------------------------------------------------------------------------------

Call the API by passing the proper parameters to the [/messages/create](https://docs.anthropic.com/en/api/messages) endpoint.

Note that the code provided by the Workbench sets the API key in the constructor. If you set the API key as an environment variable, you can omit that line as below.

*   Python
*   TypeScript

claude\_quickstart.py

```python
import anthropic

client = anthropic.Anthropic()

message = client.messages.create(
    model="claude-3-5-sonnet-20241022",
    max_tokens=1000,
    temperature=0,
    system="You are a world-class poet. Respond only with short poems.",
    messages=[
        {
            "role": "user",
            "content": [
                {
                    "type": "text",
                    "text": "Why is the ocean salty?"
                }
            ]
        }
    ]
)
print(message.content)
```

Run the code using `python3 claude_quickstart.py` or `node claude_quickstart.js`.

Response

```python
[TextBlock(text="The ocean's salty brine,\nA tale of time and design.\nRocks and rivers, their minerals shed,\nAccumulating in the ocean's bed.\nEvaporation leaves salt behind,\nIn the vast waters, forever enshrined.", type='text')]
```

The Workbench and code examples use default model settings for: model (name), temperature, and max tokens to sample.

This quickstart shows how to develop a basic, but functional, Claude-powered application using the Console, Workbench, and API. You can use this same workflow as the foundation for much more powerful use cases.

[​](http://docs.anthropic.com/en/docs/initial-setup#next-steps)

Next steps
-----------------------------------------------------------------------------

Now that you have made your first Anthropic API request, it’s time to explore what else is possible:

[Use Case Guides --------------- End to end implementation guides for common use cases.](http://docs.anthropic.com/en/docs/about-claude/use-case-guides/overview)[Anthropic Cookbook ------------------ Learn with interactive Jupyter notebooks that demonstrate uploading PDFs, embeddings, and more.](https://github.com/anthropics/anthropic-cookbook)[Prompt Library -------------- Explore dozens of example prompts for inspiration across use cases.](http://docs.anthropic.com/en/prompt-library/library)

Was this page helpful?

YesNo

[Overview](http://docs.anthropic.com/en/docs/welcome)[Intro to Claude](http://docs.anthropic.com/en/docs/intro-to-claude)

[x](https://x.com/AnthropicAI)[linkedin](https://www.linkedin.com/company/anthropicresearch)

On this page

*   [Prerequisites](http://docs.anthropic.com/en/docs/initial-setup#prerequisites)
*   [Start with the Workbench](http://docs.anthropic.com/en/docs/initial-setup#start-with-the-workbench)
*   [Install the SDK](http://docs.anthropic.com/en/docs/initial-setup#install-the-sdk)
*   [Set your API key](http://docs.anthropic.com/en/docs/initial-setup#set-your-api-key)
*   [Call the API](http://docs.anthropic.com/en/docs/initial-setup#call-the-api)
*   [Next steps](http://docs.anthropic.com/en/docs/initial-setup#next-steps)
-----------

Title: Create a Message - Anthropic

URL Source: http://docs.anthropic.com/en/api/messages

Markdown Content:
Create a Message - Anthropic
===============
  

   

[Anthropic home page![Image 3: light logo](https://mintlify.s3.us-west-1.amazonaws.com/anthropic/logo/light.svg)![Image 4: dark logo](https://mintlify.s3.us-west-1.amazonaws.com/anthropic/logo/dark.svg)](http://docs.anthropic.com/)

English

Search...

*   [Go to claude.ai](https://claude.ai/)
*   [Research](https://www.anthropic.com/research)
*   [News](https://www.anthropic.com/news)
*   [Go to claude.ai](https://claude.ai/)

Search...

Navigation

Messages

Create a Message

[Welcome](http://docs.anthropic.com/en/home)[User Guides](http://docs.anthropic.com/en/docs/welcome)[API Reference](http://docs.anthropic.com/en/api/getting-started)[Prompt Library](http://docs.anthropic.com/en/prompt-library/library)[Release Notes](http://docs.anthropic.com/en/release-notes/overview)[Developer Newsletter](http://docs.anthropic.com/en/developer-newsletter/overview)

*   [Developer Console](https://console.anthropic.com/)
*   [Developer Discord](https://www.anthropic.com/discord)
*   [Support](https://support.anthropic.com/)

##### Using the API

*   [Getting started](http://docs.anthropic.com/en/api/getting-started)
*   [IP addresses](http://docs.anthropic.com/en/api/ip-addresses)
*   [Versions](http://docs.anthropic.com/en/api/versioning)
*   [Errors](http://docs.anthropic.com/en/api/errors)
*   [Rate limits](http://docs.anthropic.com/en/api/rate-limits)
*   [Client SDKs](http://docs.anthropic.com/en/api/client-sdks)
*   [Supported regions](http://docs.anthropic.com/en/api/supported-regions)
*   [Getting help](http://docs.anthropic.com/en/api/getting-help)

##### Anthropic APIs

*   Messages
    
    *   [POST Create a Message](http://docs.anthropic.com/en/api/messages)
    *   [POST Count Message tokens](http://docs.anthropic.com/en/api/messages-count-tokens)
    *   [Streaming Messages](http://docs.anthropic.com/en/api/messages-streaming)
    *   [Migrating from Text Completions](http://docs.anthropic.com/en/api/migrating-from-text-completions-to-messages)
    *   [Messages examples](http://docs.anthropic.com/en/api/messages-examples)
*   Models
    
*   Message Batches
    
*   Text Completions (Legacy)
    
*   Admin API
    

##### Amazon Bedrock API

*   [Amazon Bedrock API](http://docs.anthropic.com/en/api/claude-on-amazon-bedrock)

##### Vertex AI

*   [Vertex AI API](http://docs.anthropic.com/en/api/claude-on-vertex-ai)

Messages

Create a Message
================

Send a structured list of input messages with text and/or image content, and the model will generate the next message in the conversation.

The Messages API can be used for either single queries or stateless multi-turn conversations.

POST

/

v1

/

messages

#### Headers

[​](http://docs.anthropic.com/en/api/messages#parameter-anthropic-beta)

anthropic-beta

string\[\]

Optional header to specify the beta version(s) you want to use.

To use multiple betas, use a comma separated list like `beta1,beta2` or specify the header multiple times for each beta.

[​](http://docs.anthropic.com/en/api/messages#parameter-anthropic-version)

anthropic-version

string

required

The version of the Anthropic API you want to use.

Read more about versioning and our version history [here](https://docs.anthropic.com/en/api/versioning).

[​](http://docs.anthropic.com/en/api/messages#parameter-x-api-key)

x-api-key

string

required

Your unique API key for authentication.

This key is required in the header of all API requests, to authenticate your account and access Anthropic's services. Get your API key through the [Console](https://console.anthropic.com/settings/keys). Each key is scoped to a Workspace.

#### Body

application/json

[​](http://docs.anthropic.com/en/api/messages#body-model)

model

string

required

The model that will complete your prompt.

See [models](https://docs.anthropic.com/en/docs/models-overview) for additional details and options.

Required string length: `1 - 256`

[​](http://docs.anthropic.com/en/api/messages#body-messages)

messages

object\[\]

required

Input messages.

Our models are trained to operate on alternating `user` and `assistant` conversational turns. When creating a new `Message`, you specify the prior conversational turns with the `messages` parameter, and the model then generates the next `Message` in the conversation. Consecutive `user` or `assistant` turns in your request will be combined into a single turn.

Each input message must be an object with a `role` and `content`. You can specify a single `user`\-role message, or you can include multiple `user` and `assistant` messages.

If the final message uses the `assistant` role, the response content will continue immediately from the content in that message. This can be used to constrain part of the model's response.

Example with a single `user` message:

```json
[{"role": "user", "content": "Hello, Claude"}]
```

Example with multiple conversational turns:

```json
[
  {"role": "user", "content": "Hello there."},
  {"role": "assistant", "content": "Hi, I'm Claude. How can I help you?"},
  {"role": "user", "content": "Can you explain LLMs in plain English?"},
]
```

Example with a partially-filled response from Claude:

```json
[
  {"role": "user", "content": "What's the Greek name for Sun? (A) Sol (B) Helios (C) Sun"},
  {"role": "assistant", "content": "The best answer is ("},
]
```

Each input message `content` may be either a single `string` or an array of content blocks, where each block has a specific `type`. Using a `string` for `content` is shorthand for an array of one content block of type `"text"`. The following input messages are equivalent:

```json
{"role": "user", "content": "Hello, Claude"}
```

```json
{"role": "user", "content": [{"type": "text", "text": "Hello, Claude"}]}
```

Starting with Claude 3 models, you can also send image content blocks:

```json
{"role": "user", "content": [
  {
    "type": "image",
    "source": {
      "type": "base64",
      "media_type": "image/jpeg",
      "data": "/9j/4AAQSkZJRg...",
    }
  },
  {"type": "text", "text": "What is in this image?"}
]}
```

We currently support the `base64` source type for images, and the `image/jpeg`, `image/png`, `image/gif`, and `image/webp` media types.

See [examples](https://docs.anthropic.com/en/api/messages-examples#vision) for more input examples.

Note that if you want to include a [system prompt](https://docs.anthropic.com/en/docs/system-prompts), you can use the top-level `system` parameter — there is no `"system"` role for input messages in the Messages API.

Show child attributes

[​](http://docs.anthropic.com/en/api/messages#body-messages-role)

messages.role

enum<string\>

required

Available options:

`user`,

`assistant`

[​](http://docs.anthropic.com/en/api/messages#body-messages-content)

messages.content

required

[​](http://docs.anthropic.com/en/api/messages#body-max-tokens)

max\_tokens

integer

required

The maximum number of tokens to generate before stopping.

Note that our models may stop _before_ reaching this maximum. This parameter only specifies the absolute maximum number of tokens to generate.

Different models have different maximum values for this parameter. See [models](https://docs.anthropic.com/en/docs/models-overview) for details.

Required range: `x > 1`

[​](http://docs.anthropic.com/en/api/messages#body-metadata)

metadata

object

An object describing metadata about the request.

Show child attributes

[​](http://docs.anthropic.com/en/api/messages#body-metadata-user-id)

metadata.user\_id

string | null

An external identifier for the user who is associated with the request.

This should be a uuid, hash value, or other opaque identifier. Anthropic may use this id to help detect abuse. Do not include any identifying information such as name, email address, or phone number.

Maximum length: `256`

[​](http://docs.anthropic.com/en/api/messages#body-stop-sequences)

stop\_sequences

string\[\]

Custom text sequences that will cause the model to stop generating.

Our models will normally stop when they have naturally completed their turn, which will result in a response `stop_reason` of `"end_turn"`.

If you want the model to stop generating when it encounters custom strings of text, you can use the `stop_sequences` parameter. If the model encounters one of the custom sequences, the response `stop_reason` value will be `"stop_sequence"` and the response `stop_sequence` value will contain the matched stop sequence.

[​](http://docs.anthropic.com/en/api/messages#body-stream)

stream

boolean

Whether to incrementally stream the response using server-sent events.

See [streaming](https://docs.anthropic.com/en/api/messages-streaming) for details.

[​](http://docs.anthropic.com/en/api/messages#body-system)

system

System prompt.

A system prompt is a way of providing context and instructions to Claude, such as specifying a particular goal or role. See our [guide to system prompts](https://docs.anthropic.com/en/docs/system-prompts).

[​](http://docs.anthropic.com/en/api/messages#body-temperature)

temperature

number

Amount of randomness injected into the response.

Defaults to `1.0`. Ranges from `0.0` to `1.0`. Use `temperature` closer to `0.0` for analytical / multiple choice, and closer to `1.0` for creative and generative tasks.

Note that even with `temperature` of `0.0`, the results will not be fully deterministic.

Required range: `0 < x < 1`

[​](http://docs.anthropic.com/en/api/messages#body-tool-choice)

tool\_choice

object

How the model should use the provided tools. The model can use a specific tool, any available tool, or decide by itself.

*   Auto
*   Any
*   Tool

Show child attributes

[​](http://docs.anthropic.com/en/api/messages#body-tool-choice-type)

tool\_choice.type

enum<string\>

required

Available options:

`auto`

[​](http://docs.anthropic.com/en/api/messages#body-tool-choice-disable-parallel-tool-use)

tool\_choice.disable\_parallel\_tool\_use

boolean

Whether to disable parallel tool use.

Defaults to `false`. If set to `true`, the model will output at most one tool use.

[​](http://docs.anthropic.com/en/api/messages#body-tools)

tools

object\[\]

Definitions of tools that the model may use.

If you include `tools` in your API request, the model may return `tool_use` content blocks that represent the model's use of those tools. You can then run those tools using the tool input generated by the model and then optionally return results back to the model using `tool_result` content blocks.

Each tool definition includes:

*   `name`: Name of the tool.
*   `description`: Optional, but strongly-recommended description of the tool.
*   `input_schema`: [JSON schema](https://json-schema.org/) for the tool `input` shape that the model will produce in `tool_use` output content blocks.

For example, if you defined `tools` as:

```json
[
  {
    "name": "get_stock_price",
    "description": "Get the current stock price for a given ticker symbol.",
    "input_schema": {
      "type": "object",
      "properties": {
        "ticker": {
          "type": "string",
          "description": "The stock ticker symbol, e.g. AAPL for Apple Inc."
        }
      },
      "required": ["ticker"]
    }
  }
]
```

And then asked the model "What's the S&P 500 at today?", the model might produce `tool_use` content blocks in the response like this:

```json
[
  {
    "type": "tool_use",
    "id": "toolu_01D7FLrfh4GYq7yT1ULFeyMV",
    "name": "get_stock_price",
    "input": { "ticker": "^GSPC" }
  }
]
```

You might then run your `get_stock_price` tool with `{"ticker": "^GSPC"}` as an input, and return the following back to the model in a subsequent `user` message:

```json
[
  {
    "type": "tool_result",
    "tool_use_id": "toolu_01D7FLrfh4GYq7yT1ULFeyMV",
    "content": "259.75 USD"
  }
]
```

Tools can be used for workflows that include running client-side tools and functions, or more generally whenever you want the model to produce a particular JSON structure of output.

See our [guide](https://docs.anthropic.com/en/docs/tool-use) for more details.

*   Tool
*   ComputerUseTool\_20241022
*   BashTool\_20241022
*   TextEditor\_20241022

Show child attributes

[​](http://docs.anthropic.com/en/api/messages#body-tools-type)

tools.type

enum<string\> | null

Available options:

`custom`

[​](http://docs.anthropic.com/en/api/messages#body-tools-description)

tools.description

string

Description of what this tool does.

Tool descriptions should be as detailed as possible. The more information that the model has about what the tool is and how to use it, the better it will perform. You can use natural language descriptions to reinforce important aspects of the tool input JSON schema.

[​](http://docs.anthropic.com/en/api/messages#body-tools-name)

tools.name

string

required

Name of the tool.

This is how the tool will be called by the model and in tool\_use blocks.

Required string length: `1 - 64`

[​](http://docs.anthropic.com/en/api/messages#body-tools-input-schema)

tools.input\_schema

object

required

[JSON schema](https://json-schema.org/) for this tool's input.

This defines the shape of the `input` that your tool accepts and that the model will produce.

Show child attributes

[​](http://docs.anthropic.com/en/api/messages#body-tools-input-schema-type)

tools.input\_schema.type

enum<string\>

required

Available options:

`object`

[​](http://docs.anthropic.com/en/api/messages#body-tools-input-schema-properties)

tools.input\_schema.properties

object | null

[​](http://docs.anthropic.com/en/api/messages#body-tools-cache-control)

tools.cache\_control

object | null

Show child attributes

[​](http://docs.anthropic.com/en/api/messages#body-tools-cache-control-type)

tools.cache\_control.type

enum<string\>

required

Available options:

`ephemeral`

[​](http://docs.anthropic.com/en/api/messages#body-top-k)

top\_k

integer

Only sample from the top K options for each subsequent token.

Used to remove "long tail" low probability responses. [Learn more technical details here](https://towardsdatascience.com/how-to-sample-from-language-models-682bceb97277).

Recommended for advanced use cases only. You usually only need to use `temperature`.

Required range: `x > 0`

[​](http://docs.anthropic.com/en/api/messages#body-top-p)

top\_p

number

Use nucleus sampling.

In nucleus sampling, we compute the cumulative distribution over all the options for each subsequent token in decreasing probability order and cut it off once it reaches a particular probability specified by `top_p`. You should either alter `temperature` or `top_p`, but not both.

Recommended for advanced use cases only. You usually only need to use `temperature`.

Required range: `0 < x < 1`

#### Response

200 - application/json

[​](http://docs.anthropic.com/en/api/messages#response-id)

id

string

required

Unique object identifier.

The format and length of IDs may change over time.

[​](http://docs.anthropic.com/en/api/messages#response-type)

type

enum<string\>

default: messagerequired

Object type.

For Messages, this is always `"message"`.

Available options:

`message`

[​](http://docs.anthropic.com/en/api/messages#response-role)

role

enum<string\>

default: assistantrequired

Conversational role of the generated message.

This will always be `"assistant"`.

Available options:

`assistant`

[​](http://docs.anthropic.com/en/api/messages#response-content)

content

object\[\]

required

Content generated by the model.

This is an array of content blocks, each of which has a `type` that determines its shape.

Example:

```json
[{"type": "text", "text": "Hi, I'm Claude."}]
```

If the request input `messages` ended with an `assistant` turn, then the response `content` will continue directly from that last turn. You can use this to constrain the model's output.

For example, if the input `messages` were:

```json
[
  {"role": "user", "content": "What's the Greek name for Sun? (A) Sol (B) Helios (C) Sun"},
  {"role": "assistant", "content": "The best answer is ("}
]
```

Then the response `content` might be:

```json
[{"type": "text", "text": "B)"}]
```

*   Text
*   Tool Use

Show child attributes

[​](http://docs.anthropic.com/en/api/messages#response-content-type)

content.type

enum<string\>

default: textrequired

Available options:

`text`

[​](http://docs.anthropic.com/en/api/messages#response-content-text)

content.text

string

required

Maximum length: `5000000`

[​](http://docs.anthropic.com/en/api/messages#response-model)

model

string

required

The model that handled the request.

Required string length: `1 - 256`

[​](http://docs.anthropic.com/en/api/messages#response-stop-reason)

stop\_reason

enum<string\> | null

required

The reason that we stopped.

This may be one the following values:

*   `"end_turn"`: the model reached a natural stopping point
*   `"max_tokens"`: we exceeded the requested `max_tokens` or the model's maximum
*   `"stop_sequence"`: one of your provided custom `stop_sequences` was generated
*   `"tool_use"`: the model invoked one or more tools

In non-streaming mode this value is always non-null. In streaming mode, it is null in the `message_start` event and non-null otherwise.

Available options:

`end_turn`,

`max_tokens`,

`stop_sequence`,

`tool_use`

[​](http://docs.anthropic.com/en/api/messages#response-stop-sequence)

stop\_sequence

string | null

required

Which custom stop sequence was generated, if any.

This value will be a non-null string if one of your custom stop sequences was generated.

[​](http://docs.anthropic.com/en/api/messages#response-usage)

usage

object

required

Billing and rate-limit usage.

Anthropic's API bills and rate-limits by token counts, as tokens represent the underlying cost to our systems.

Under the hood, the API transforms requests into a format suitable for the model. The model's output then goes through a parsing stage before becoming an API response. As a result, the token counts in `usage` will not match one-to-one with the exact visible content of an API request or response.

For example, `output_tokens` will be non-zero, even for an empty string response from Claude.

Show child attributes

[​](http://docs.anthropic.com/en/api/messages#response-usage-input-tokens)

usage.input\_tokens

integer

required

The number of input tokens which were used.

Required range: `x > 0`

[​](http://docs.anthropic.com/en/api/messages#response-usage-cache-creation-input-tokens)

usage.cache\_creation\_input\_tokens

integer | null

required

The number of input tokens used to create the cache entry.

Required range: `x > 0`

[​](http://docs.anthropic.com/en/api/messages#response-usage-cache-read-input-tokens)

usage.cache\_read\_input\_tokens

integer | null

required

The number of input tokens read from the cache.

Required range: `x > 0`

[​](http://docs.anthropic.com/en/api/messages#response-usage-output-tokens)

usage.output\_tokens

integer

required

The number of output tokens which were used.

Required range: `x > 0`

Was this page helpful?

YesNo

[Getting help](http://docs.anthropic.com/en/api/getting-help)[Count Message tokens](http://docs.anthropic.com/en/api/messages-count-tokens)

[x](https://x.com/AnthropicAI)[linkedin](https://www.linkedin.com/company/anthropicresearch)