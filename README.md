### Nihar Damera

I build LLM agents and the evaluations that decide whether to trust them:
workflow-first agents, retrieval with checked citations, and small models
tuned with SFT, DPO and GRPO. Every number below links to a committed eval file
in its repo.

**[CREO](https://github.com/nihardamera/creo-agent)**: an alert-remediation agent.
Runbooks are configuration rather than retrieval, the model is called only where
judgement is needed, and no server changes without a named human approving that
exact action. On 815 held-out synthetic alerts, end-to-end correctness went from
93% to 99.3%, with 0 unsafe actions and 100 of 100 prompt-injection attacks stopped.
[Code](https://github.com/nihardamera/creo-agent) ·
[2-minute video](https://github.com/nihardamera/creo-agent/blob/main/docs/demo/creo-demo.mp4)

<img src="https://github.com/nihardamera/creo-agent/raw/main/docs/demo/approval.gif" width="640" alt="CREO waits, proposes a restart, a named approver approves, and the run resolves">

**[creo-classify-0.6B](https://huggingface.co/nihar-damera/creo-classify-0.6b)**:
Claude Haiku distilled into Qwen3-0.6B, then GRPO with a safety penalty,
including a caught case of reward hacking. Inside CREO it scores 100% against
99.1% for the API model on held-out synthetic alerts, at 0.71 s p50 on a laptop,
with no API cost in the normal path.
[Model](https://huggingface.co/nihar-damera/creo-classify-0.6b) ·
[Report](https://github.com/nihardamera/creo-agent/blob/main/docs/P4_REPORT.md)

**[Commit Suggestor](https://github.com/nihardamera/Commit-Suggestor)**: a 1.5B code
model that writes commit subjects from diffs. ROUGE-L rose from 21.1 to 31.1 on
three projects it never trained on, and DPO took generic subjects from 8.4% to 0%.
[Code](https://github.com/nihardamera/Commit-Suggestor) ·
[Model](https://huggingface.co/nihar-damera/commit-suggestor) ·
[Demo page](https://huggingface.co/spaces/nihar-damera/commit-suggestor-demo)

**[RegRadar](https://github.com/nihardamera/RegRadar)**: cited RAG over 290 Reserve
Bank of India circulars. Hybrid BM25 + dense retrieval reaches 92.9% held-out
recall@10 against 87.1% for dense-only, and code checks every citation before
an answer is shown.
[Code](https://github.com/nihardamera/RegRadar) ·
[Demo](https://huggingface.co/spaces/nihar-damera/RegRadar)

Reach me at nihar.damera434@gmail.com or on
[LinkedIn](https://www.linkedin.com/in/nihar-damera/). Models and demos are on
[Hugging Face](https://huggingface.co/nihar-damera).
