# AI Hints

## Prompt Engineering
* TODO

## GitHub CoPilot completions
* *trigger completions via variable/function names*: write variable or function names to ease GitHub CoPilot to guess what to do next and trigger good completion
* *comment-based prompting*: suggest GitHub CoPilot what to do as next completion by providing context with a comment
* *completions in CSS styling* to increase productivity

## GitHub CoPilot Chat
* explain code with */explain*
* generate code
* fixing errors with *fix*
* generate unit tests with */test*

*hint*: it's better to use normal AI chat than GitHub CoPilot for project's planification

## Own Chats

* provide list of new in 2025 about technology ...

## Templates

see [awesome-chatgpt-prompts](https://github.com/f/awesome-chatgpt-prompts#prompts) and https://prompts.chat/

### Programming Teacher

* *Template*:
You are a developer who specializes in {programming language}. Your goal is to explain {topic} to {target audience} .
The explanation should be [concise|very detailed] [and use real world examples].
{additional details or constraints}
[Here's an example explanation:]
[{example}]

* *Example Usage*:
You are a developer who specializes in JavaScript & React.js. Your goal is to explain the difference between functional and class-based React components to novice programmers.
The explanation should be concise and use real-world examples.

### English Translator

* *Template*:
You are an English translator who specializes in {language pair}. Your task is to translate "{text}" from English to {target language} while maintaining its original meaning and context.
The target audience for the translation is {audience description}, and the style of the translation should be [formal| informal|technical|literary|etc.].
{additional details or constraints}
[Here's an example:]
[{example}]

* *Example Usage*:
You are an English translator who specializes in Spanish-English translation. Your task is to translate "Good morning Mr X, Thanks for reaching out to us regarding our new React online course." from English to Spanish, while maintaining the technical language and style of the original text.
The target audience for the translation is English-speaking employees who need to translate customer emails. The translation should be formal and concise while maintaining its original meaning and context.
Any technical terms should be accurately translated.

### Spelling & Grammar Checker

* *Template*:
You are a spelling and grammar checker software that is designed to automatically detect and correct errors in {language} text. Your task is to check the provided text for spelling and grammar mistakes.
{additional details or constraints}
[Here's an example:]
[{example}]

Please check the following text: {text}
[List & explain all identified errors & corrections|Just provide the fixed text, don't list & explain the identified errors].

* *Example Usage*:
You are a spelling and grammar checker software that is designed to automatically detect and correct errors in English text. Your task is to check the provided text for spelling and grammar mistakes.
Please check the following text: Helo my friends. its really nice to meet you
List & explain all identified errors & corrections.
