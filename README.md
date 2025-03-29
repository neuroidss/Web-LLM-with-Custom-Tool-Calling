# Web-LLM-with-Custom-Tool-Calling

https://neuroidss.github.io/Web-LLM-with-Custom-Tool-Calling

```
make llm chat with custom tool calling, as native tool calling not yet supported in webllm for qwen. in html&css&js all in single html block.

use web-llm. 
<script type="module">
import * as webllm from "https://esm.run/@mlc-ai/web-llm";
                engine = await webllm.CreateMLCEngine(
                    "Qwen2.5-Coder-7B-Instruct-q4f32_1-MLC",
                    { initProgressCallback: reportProgress }
                );
                don't use appConfig.
                with reportProgress use progress.progress if needed.
use engine.chat.completions.create but without its tools, use custom tools, stream: false, also set temperature in it.

add in llm tools list for chatbot llm tool_creation_tool with parameters 'name' and 'description' and which calls engine chat create to create js function which makes what in 'description' and named as 'name', and evaluates this new js function, then creates llm tool with same name and description and parameters which was used in new created js function, and adding new llm tool in available llm tools list for chatbot, js function should take a single parameters object as named array. use another role instead of role tool. as system prompt can be placed only on first message, for tools declaration use assistant prompt but place it each time before new user message in history, but don't keep this tools usage message in history as it will be always updated. last message should be from user. don't use system role anywhere but first message. for created tools js functions and json parameters use only code inside blocks '''javascript ''', '''json ''', remove these block markers. if using, json block for tools use detection then remove '''json ''' block markers before parsing.

make ability to switch between Qwen2.5-Coder-7B-Instruct-q4f32_1-MLC and Qwen2.5-Coder-3B-Instruct-q4f32_1-MLC, and set temperature of generation.

initialize after all elements created.
```
