# AI Hints

## Prompt Engineering

*general informations*
* good prompts: "be specific" - "add useful context" - "add examples" - "split complex tasks"
** iterate to improve the result BUT don't get lost in "iteration hell"
* two main goals of prompt engineering is to control output **content** (an article) and optionaly control output **format** (e.g. markdown)
* a good prompt include a detailed task description (or goal, question) and context (role, relevant information, examples, contraints)
* complex (multi-task) prompts should be avoided
* fine-tune & adjust output with follow-up question/task in chat (e.g. add links)

*techniques*
* zero-shot Prompting without providing examples
* one-, few-shot prompting
  * ... by providing examples to fine-tune the result, style and content
  * examples should be separated by some characters (e.g. """ or <example1>)
  * put first context and examples and then instruction at last (sequence to be completed)
  ```
  Act as ... that ...
  Here is a few examples:
  <example-1>....</example-1>
  <example-2>...</example-2>

  Do ...  
  ```
  * example can contain expected output:
  ```
  I need to translate an English text to German
  Please analyze the text and translate it on a word-by-word basis.
  
  For example:
  <english-text>The sun is shining.</english-text>
  
  <translated-output>
  The: Die
  Sun: Sonne
  is: ist
  shining: scheint
  </translated-output>

  Here's the text I want you to translate:
  <input>
  </input>
  ```
  * finetuning model as alternative to few-shot prompting
    * finetune for a specific task repeated regurlaly 
    * ... finetune is expensive
    * ... finetune can produce worse results with other tasks
* using delimiters to structure prompt
* contextual prompting
  * by including relevant information / data in prompt or as attachment files (e.g. an article)
* chain-of-thought prompting
  * ... by adding following line in prompt: 
  ```
  think step-by-step, outline your solution process (in detail) and derive the solution step-by-step therefore.
  ```
  * chain-of-thought helps e.g. for math/logical problem to increase correct results
  * reasoning models include chain-of-thought internally --> please not use chain-of-thought explicitly in that case   
* split complex problems into simpler ones
  * ... with multiple prompts/tasks in the same chat to achieve the final complex task 
* ask-before-answer prompting
  * ... by adding following line in prompt: 
  ```
  ask any clarifying questions you want me to clarify before answering.
  ```
* persona prompting
  * ... by adding a role as first-line in prompt, e.g.
  ```
  You are an expert developer.
  ```
  * ... role can have more detail
  ```
  You are an expert developer. You are friendly but you're also aware of your status as a leader in AI-space.
  ```
  * ... detail about target audience might help
  ```
  You are an expert developer. You are friendly but you're also aware of your status as a leader in AI-space.
  You are also aware of the fact that many people are scared of AI (especially of AI taking their job).
  ```
* self-reflective prompting
  * an existing result exists, ask AI to improve its content with following prompt:
  ```
  analyze the output. What's goot about it, what's bad? How could it be improved?
  ``` 
* negative prompting
  * ... by adding following line in prompt:
  ```
  don't ...
  ```
  * e.g.
  ```
  don't cover any AI related subjects.
  ```
* controlling the output format
  * ... by adding following line in prompt, e.g.
  ```
  Output the data in CSV format. Just output the data, no other text. No extra explanations.
  ```
  * example 2:
  ```
  Output the text as unparsed Markdown so that i can copy it into my own Markdown-parsing pipeline.
  ```
  * example 3:
  ```
  Output the list like this:
  TITLE: short explanation
  ```
* AI can help with prompting
  ```
  I want to ask a generative AI model (like ChatGPT) to write a blog post about ...

  How would a good prompt look like? Give me detailed instructions and example.
  ```
* using provider-specific prompt guides
  * e.g. read official doc of OpenAI or anthropic

### Prompts Templates

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

[*Go to top*](#AI-Hints)

*(last update september 2025*
