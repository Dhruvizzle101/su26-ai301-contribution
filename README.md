# su26-ai301-contribution

# CodePath AI301 Open Source Contribution

**Student:** Dhruv Kothari  
**GitHub:** Dhruvizzle101  
**Program:** CodePath Advanced AI Open-Source Capstone (AI301) — Summer 2026  
**Status:** Phase IV Complete

---

## Phase I: Issue Selection

**Issue:** tutorials : list for llama.cpp  
**Issue Link:** https://github.com/ggml-org/llama.cpp/issues/13523
**Comment on Issue:** https://github.com/ggml-org/llama.cpp/issues/13523#issuecomment-4617822754
**Repository:** ggml-org/llama.cpp  
**My specific tutorial:** Apple A-chipsets — how to estimate a suitable model size

**Problem Summary:**  
The llama.cpp project maintains a list of community-written tutorials and guides. One unclaimed tutorial topic is how to estimate a suitable model size for Apple A-chipsets (M1/M2/M3/M4), which is a common question for users running LLMs locally on Mac hardware.

**Why I chose this issue:**  
I chose this because I am a Mac user working on Apple Silicon hardware daily, so I have firsthand experience with the challenges of running LLMs locally on A-chipsets. It sits at the intersection of LLM inference and Apple Silicon hardware, which is directly relevant to my work in CodePath's AI301 capstone. I also have hands-on experience with LLM orchestration from my internship at HumanityAI, which will help me write an accurate and practical guide that other Mac users can actually use.

---

## Phase II: Understanding the Issue

### Environment Setup
Built llama.cpp from source on MacBook Air (Apple Silicon, arm64) using 
CMake and Metal backend. No major issues — Metal is enabled by default on 
Mac. Build completed successfully with AppleClang 17.0.0.

**Working Branch:** https://github.com/Dhruvizzle101/llama.cpp/tree/tutorial-apple-chipsets-13523

### Steps to Reproduce
1. Install llama.cpp on a Mac with Apple Silicon
2. Attempt to find official documentation on which model size fits your chip
3. **Expected:** A clear guide explaining model size estimation for Apple Silicon
4. **Actual:** No such guide exists in the llama.cpp documentation

### Solution Plan

**Understand:** 
Mac users on Apple Silicon have no official guide for estimating which LLM 
model sizes will fit their unified memory. Users either crash their system 
downloading models too large, or run unnecessarily small models not knowing 
they could run something better.

**Match:** 
The llama.cpp project maintains a tutorials list (issue #13523) where 
community members contribute practical guides. Existing tutorials follow a 
clear Markdown format in GitHub Discussions under "Show and Tell."

**Plan:**
1. Write tutorial covering unified memory architecture on Apple Silicon
2. Document the model size formula: parameters × bytes per weight
3. Create a quantization comparison table (Q2/Q4/Q6/Q8/F16)
4. Build a lookup table mapping Mac RAM tiers to runnable model sizes
5. Add practical llama.cpp commands for testing models before downloading
6. Post as a GitHub Discussion in llama.cpp under Show and Tell
7. Link back to issue #13523

**Implement:** 
https://github.com/Dhruvizzle101/llama.cpp/tree/tutorial-apple-chipsets-13523

**Review:** 
Will follow llama.cpp CONTRIBUTING.md guidelines and match the format of 
existing tutorials in the project.

**Evaluate:** 
Tutorial will be verified by running actual llama.cpp commands on my 
MacBook Air and confirming all model size estimates are accurate.

---

## Phase III: Build

### Implementation Notes

**What I built:**
- Wrote a complete tutorial on Apple A-chipsets model size estimation for llama.cpp
- Tutorial covers unified memory architecture, model size formula, quantization 
  levels, Mac RAM lookup table, practical llama.cpp commands, and recommendations
  by Mac memory size
- Posted as a GitHub Discussion in the llama.cpp Show and Tell section

**Code Changes:**
- Branch: https://github.com/Dhruvizzle101/llama.cpp/tree/tutorial-apple-chipsets-13523
- Tutorial file: docs/apple-chipsets-model-size-guide.md
- Discussion: https://github.com/ggml-org/llama.cpp/discussions/25065

**Testing Strategy:**
- Verified all llama.cpp commands by building and running llama.cpp locally 
  on MacBook Air with Apple Silicon
- Confirmed Metal backend is enabled by default on arm64
- All model size calculations verified manually using the formula

**Challenges Faced:**
- llama.cpp has a strict no AI-generated content policy so all tutorial 
  content was written independently
- Had to build llama.cpp from source using CMake before being able to 
  verify the commands in the tutorial
---


## Phase IV: Submit & Iterate

**PR Link:** https://github.com/ggml-org/llama.cpp/pull/25068

**PR Description:**
Added a tutorial guide for Apple Silicon Mac users on how to estimate 
a suitable model size when running LLMs with llama.cpp. The guide covers 
unified memory architecture, the model size formula, quantization levels, 
a Mac RAM lookup table, practical llama.cpp commands, and recommendations 
by Mac memory size.

**Status:** Awaiting review

**Maintainer Feedback:** None yet — PR submitted on June 26, 2026. 
Tagged @ggerganov for review.

## Learnings & Reflections

This was my first open source contribution to a major AI repository. 
The biggest challenge was adhering to llama.cpp's strict no AI-generated 
content policy, which forced me to genuinely understand the concepts of 
unified memory, quantization, and model size estimation before writing 
about them. Building llama.cpp from source and seeing it run on my own 
Mac made the tutorial more credible and accurate. I learned that open 
source contribution is less about writing perfect code and more about 
communicating clearly with maintainers and the community.


---

# Cycle 2

## Phase I: Issue Selection

**Issue:** feat req: make custom summary available over API/MCP and AI chat
**Issue Link:** https://github.com/BasedHardware/omi/issues/7478
**Repository:** BasedHardware/omi
**Comment on Issue:** [paste your comment link here]

**Problem Summary:**
Users can create custom summaries in omi with their own prompts, getting 
more precise results. However these custom summaries are not accessible 
via the API, MCP endpoints, or AI chat — only the default omi-generated 
summaries are returned. The fix is exposing custom summaries through the 
existing API endpoints alongside the default ones.

**Why I chose this issue:**
Omi is an AI wearable device app with 13k stars that processes real-world 
conversations and memories. This issue sits at the intersection of AI 
summarization and API design, which is directly relevant to my LLM 
orchestration experience at HumanityAI. The fix requires understanding 
how the backend serves summaries and extending it to include user-generated 
ones — real Python backend work with clear scope.

**Status:** Phase I Complete
