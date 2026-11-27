# Agent Architecture Resources

## Knowledge

- [Article: Effective context engineering for AI agents (Anthropic)](https://anthropic.com/engineering/effective-context-engineering-for-ai-agents)
  Context limits, compaction, note-taking, just-in-time retrieval. Use for: context and memory design.
- [Docs: Context windows](https://platform.claude.com/docs/en/build-with-claude/context-windows)
  What counts toward the window, overflow, context rot. Use for: limits and token budgeting.
- [Docs: API primer](https://platform.claude.com/docs/en/claude_api_primer)
  Statelessness of the Messages API. Use for: what is kept between calls.
- [Docs: Conversation state](https://developers.openai.com/api/docs/guides/conversation-state)
  History handling and billing of earlier input. Use for: cost of resent history.
- [Article: Contextual retrieval (Anthropic, 2024)](https://www.anthropic.com/engineering/contextual-retrieval)
  RAG steps, keyword and embedding search, chunk context. Use for: manual search design.

## Wisdom (Communities)

- [Hugging Face Forums, Beginners](https://discuss.huggingface.co/c/beginners/5)
  General AI forum where agent questions appear. Use for: critique of a memory plan.
