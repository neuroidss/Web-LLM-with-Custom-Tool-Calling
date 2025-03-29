# Web-LLM-with-Custom-Tool-Calling

https://neuroidss.github.io//Web-LLM-with-Custom-Tool-Calling

```
make llm chat with custom tool calling, as native tool calling not yet supported in webllm for qwen. in html&css&js all in single html block.

use web-llm. 
<script type="module">
import * as webllm from "https://esm.run/@mlc-ai/web-llm";
                engine = await webllm.CreateMLCEngine(
                    "Qwen2.5-Coder-3B-Instruct-q4f32_1-MLC",
                    { initProgressCallback: reportProgress }
                );
engine.chat.completions.create

add in llm tools list for chatbot llm tool_creation_tool with parameters new_tool_name and new_tool_description and which calls engine chat create to create js function which makes what in new_tool_description and named as new_tool_name, and evaluates this new js function, then creates llm tool with same name and description and parameter which was used in new created js function, and adding new llm tool in available llm tools list for chatbot. use role assistant instead fo role tool. place system prompt before all other prompts if needed.
```
