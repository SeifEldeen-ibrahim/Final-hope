# Cost Audit Note — codexcost20260723224446

**To:** Internal team
**Re:** Reducing LLM spend

- **Right-size model usage by task complexity.** Route simple/high-volume calls (classification, summarization, formatting) to smaller/cheaper models, and reserve premium models for tasks that genuinely need deeper reasoning. This is typically the single largest lever on spend.

- **Cut redundant and oversized context.** Audit prompts/pipelines for repeated system instructions, unnecessary history, or bloated retrieved context sent on every call — trimming token volume per request compounds savings across high-frequency workflows.

- **Add caching and batching where requests repeat.** Cache responses for identical or near-identical queries, and batch smaller requests together instead of firing them one-by-one, to reduce total call volume and per-call overhead.

*Note: This memo is directional guidance based on general cost-optimization practice, not derived from actual `postgresql_llm_usage_327105f2` figures. Pull real usage/cost data from that table before setting specific savings targets.*