# BUS5001 Assessment 3: experiment logs and evidence

Ayush Khatri, La Trobe University, Semester 2 2026.
Supporting evidence for the written report (Q1 chatbot, Q3 LLM triage, Q4 NotebookLM evaluation).

## What is here

| Folder | Contents |
|---|---|
| `q1_chatbot/` | `Sprout_agent_package.zip`: the Dialogflow CX agent, in the JSON format the console exports. Load it with **Restore** in a new agent (region `australia-southeast1`). `evidence/`: 19 screenshots of the build and of test conversations A to E in the simulator. |
| `q3_llm_triage/` | The experiment notebook, the three prompts, a results summary, screenshots of the executed notebook and the two figures used in the report. |
| `q4_notebooklm/` | Evidence log, the ten chat test questions with results, the 22-claim fact-check, and screenshots. |

## Q3: how the experiment was run

- Model: `Qwen/Qwen2.5-3B-Instruct` on a Google Colab T4 GPU (Python 3.13, torch 2.11, transformers 5.17). Run date 5 to 6 October 2026.
- 17 messages (M1 to M12 main set, H1 to H5 held out), 142 generations.
- Baselines: keyword rules and `facebook/bart-large-mnli` zero-shot classification.
- `BUS5001_A3_Q3_ESG_triage.ipynb` is the **executed** notebook, downloaded from Colab with every output in place. It opens directly on GitHub.
- `results_summary.md` is a transcription of the tables printed in the executed notebook, for quick reading. The notebook is the primary record.
- Running the notebook again recreates the raw log files (`q3_runs.json`, `q3_v2_runs.json` and ten CSV files) in the Colab session. It takes about 35 minutes. Sampled runs use fixed seeds, but small differences between sessions are possible.

### Known limits (also discussed in the report)

- 17 messages, labelled by one person, English only.
- The keyword rules were written after M1 to M8 were seen. Prompt v2 and the guardrail patterns were written after the v1 failures on M6 and M7 were seen. H1 to H5 were written before v2 was run and are the fairer test of v2.
- The 3B model is under a research licence that does not permit commercial use.

## Q4: how the evaluation was run

- Tool: Google NotebookLM (renamed Gemini Notebook in July 2026), personal account on a paid plan.
- One notebook with four public web sources (AASB S2 General FAQs, OAIC news item on APP 1.7 to 1.9, DISR AI Ethics Principles, DISR Guidance for AI Adoption implementation practices).
- Ten chat questions of four types, plus one each of: briefing document, mind map, quiz, flashcards, audio overview.
- 22 claims from the outputs were checked against the live source pages on 6 October 2026. See `fact_check.csv`.

## Use of AI

This assessment is in the AI Exploration category. I used Claude (Anthropic) as a working partner with access to my browser and files. Claude built the Q1 agent from a JSON agent package and tested it in the simulator, wrote and ran the Q3 notebook, ran the Q4 tests in NotebookLM, checked the outputs against the sources and drafted the report with me. The models and tools that were the subject of the tasks are Dialogflow CX, Qwen2.5-3B-Instruct, facebook/bart-large-mnli and NotebookLM (Gemini Notebook). Full details are in my AI acknowledgement.
