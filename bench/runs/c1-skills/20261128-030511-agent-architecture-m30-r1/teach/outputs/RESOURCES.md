# Agent Architecture Resources

## Knowledge

- [Article: Effective context engineering for AI agents (Anthropic Engineering)](https://anthropic.com/engineering/effective-context-engineering-for-ai-agents)
  Context rot, compaction, note-taking, just-in-time and hybrid retrieval. Primary source for lesson 1.
- [Docs: Context windows](https://platform.claude.com/docs/en/build-with-claude/context-windows)
  What counts toward the window, overflow behavior, tool-result clearing. Vendor-specific; sizes change.
- [Docs: Working with messages](https://platform.claude.com/docs/en/build-with-claude/working-with-messages)
  Stateless API and resending history (also mentions a beta thread option).
- [Docs: Memory tool](https://platform.claude.com/docs/en/agents-and-tools/tool-use/memory-tool)
  Client-side memory across conversations, with security guidance.
- [Article: Contextual Retrieval (Anthropic, 2024)](https://anthropic.com/news/contextual-retrieval)
  Chunking, BM25 plus embeddings, when to skip retrieval, test results.
- [Docs: Glossary](https://platform.claude.com/docs/en/about-claude/glossary)
  Tokens, context window, RAG.

## Wisdom (Communities)

- [Hugging Face Agents Course: Discord guide](https://huggingface.co/learn/agents-course/unit0/discord101)
  Seen in search results, not opened. Use for: feedback on agent designs.

## Gaps

- All the technical sources read so far come from one vendor. A vendor-neutral source on agent memory would help, since the mission does not compare vendors.
