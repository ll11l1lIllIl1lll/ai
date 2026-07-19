# this is a custom modify, ref. @ai-sdk/openai-compatible readme
## Example

```ts
import { createOpenAICompatible } from '@ai-sdk/openai-compatible';
import { generateText } from 'ai';

const { text } = await generateText({
  model: createOpenAICompatible({
    baseURL: 'https://bad-openai-endpoint.example.com/v1',
    name: 'example',
    apiKey: process.env.MY_API_KEY,
    onNonStandardStreamChunk: "skip-unknown", // 'error' fail-close, 'skip-unknown' ignores non-completion, 'skip-all' fail-silent
  }).chatModel('meta-llama/Llama-3-70b-chat-hf'),
  prompt: 'Write a vegetarian lasagna recipe for 4 people.',
});
```
