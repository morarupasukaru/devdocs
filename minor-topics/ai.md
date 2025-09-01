# AI Hints

## Prompt Engineering 
see [Prompt Engineering Guide](https://www.promptingguide.ai/)

*general informations*
* two main goals of prompt engineering is to control output **content** (an article) and optionaly control output **format** (e.g. markdown)
* a good prompt include a detailed task description (or goal, question) and context (role, relevant information, examples, contraints)
* complex (multi-task) prompts should be avoided
* fine-tune & adjust output with follow-up question/task in chat (e.g. add links)

*techniques*
* [zero-shot Prompting](https://www.promptingguide.ai/techniques/zeroshot), [one-, few-shot prompting](https://www.promptingguide.ai/techniques/fewshot)
  * finetuning vs few-shot prompting
* using delimiters to structure prompt
* contextual prompting (including relevant data + information)
* [chain-of-thought prompting](https://www.promptingguide.ai/techniques/cot)
  * reasoning models & chain-of-thought prompting
* split complex problems into simpler ones
* ask-before-answer prompting
* persona prompting
* [self-reflective prompting](https://www.promptingguide.ai/techniques/reflexion)
* negative prompting
* controlling the output format

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

## Prompts Templates

see [awesome-chatgpt-prompts](https://github.com/f/awesome-chatgpt-prompts#prompts):
* [Act as a UX/UI Developer](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-a-uxui-developer)
* [Act as a Web Design Consultant](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-a-web-design-consultant)
* [Act as a Text Based Adventure Game](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-a-text-based-adventure-game)
* [Act as a Fancy Title Generator](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-a-fancy-title-generator)
* [Act as an Educational Content Creator](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-an-educational-content-creator)
* [Act as an Ascii Artist](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-an-ascii-artist)
* [Act as a Fullstack Software Developer](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-a-fullstack-software-developer)
* [Act as a Senior Frontend Developer](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-a-senior-frontend-developer)
* [Act as a Regex Generator](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-a-regex-generator)
* [Act as a Accessibility Auditor](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-a-accessibility-auditor)
* [Act as a Cover Letter](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-a-cover-letter)
* [Act as a Japanese Kanji Quiz Machine](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-a-japanese-kanji-quiz-machine)
* [Act as a Unit Tester Assistant](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-a-unit-tester-assistant)
* [Act as a Recruiter](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-a-recruiter)
* [Act as Career Coach](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-career-coach)
* [Act as Children's Book Creator](https://github.com/f/awesome-chatgpt-prompts?tab=readme-ov-file#act-as-childrens-book-creator)
