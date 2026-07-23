# Cost Audit Note — codexcost20260723183107

**To:** Internal team
**Re:** Reducing LLM spend

A few quick opportunities worth pursuing based on typical cost drivers in LLM usage:

- **Right-size model selection per task** — route simple, high-volume tasks (classification, extraction, short replies) to cheaper/smaller models, and reserve premium models for tasks that genuinely need deeper reasoning or long context.
- **Trim prompt and context bloat** — audit system prompts, retrieved context, and conversation history for unnecessary length; shorter inputs reduce token cost on every call, especially at scale.
- **Cache and dedupe repeated calls** — add response caching for repeated/near-identical queries and batch requests where possible, instead of re-running the same prompt against the model each time.

*Note: this memo is a general framework — pair it with actual usage data (e.g. from `postgresql_llm_usage_327105f2`) to identify which specific tasks/models are driving the highest spend before prioritizing action.*