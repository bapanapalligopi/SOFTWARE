# The Explore → Plan → Code → Commit Workflow

If you take one thing away from this course, let it be this workflow:

## Explore → Plan → Code → Commit

Many developers immediately ask Claude Code to start writing code. While this can work, it often leads to unnecessary revisions and course corrections later.

Following this workflow helps Claude understand the problem first, develop a strategy, implement the solution, and then prepare it for deployment.

---

# 1. Explore

The first step is understanding the project and gathering context.

Claude Code performs best when it has enough information about:

* Your codebase structure
* Existing architecture
* Dependencies
* Coding patterns
* Current implementation details

### Why Explore First?

Without context, Claude may:

* Make incorrect assumptions
* Duplicate existing functionality
* Miss important constraints
* Create solutions that don't fit the project

Exploration helps Claude understand the environment before making decisions.

---

# 2. Plan

The fastest way to combine exploration and planning is with **Plan Mode**.

### Entering Plan Mode

Press:

```text id="8wxypl"
Shift + Tab
```

until you see:

```text id="47lmqp"
Plan Mode
```

displayed beneath the input box.

### Example Planning Prompt

```text id="o0m5zs"
I need to add WebP conversion to our image upload pipeline. Figure out where in the pipeline it should happen, whether we need new dependencies, and how to approach it.
```

### What Claude Does

In Plan Mode, Claude:

* Reads relevant files
* Examines your architecture
* Researches implementation approaches
* Searches for documentation when necessary
* Identifies dependencies
* Creates a step-by-step implementation plan

### Important Limitation

While in Plan Mode:

* Claude cannot edit files
* Claude cannot modify code
* Claude focuses exclusively on analysis and planning

This makes it a safe environment for evaluating ideas.

---

# Plan Review

📷 **Image: Claude Code Presenting an Implementation Plan**

![Image](https://images.openai.com/static-rsc-4/f-COUvaM9h9rF0IpSCohPEQW6v_v1S-TStd8PH_BkptREGrJvyOlSw6xSRRPMAEodt_1jrmGZq_IND-wnGjFp0Tze__iWDZXayf3Y2haBy24qT0pI3FG9kjJcRc79emgS5tgh_mIJsp-n33RusVgPy0tYUhNXvvTIAAASGVERKKr2eDn6cx0sfD4k7aJS1cr?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/yyM3_kiI_XoXBr3sQ1b9ElsuvX7bklUls2R3kiV-s6TS10LLV2h1NKHazQfeL5O9KznyLI2BpkePGOsvmFRDZsrC1cfJhuqRXR-ZlQM7LqlX33immsWfxKWNTB1P8CPZsuLNoz4INsCcuIOCI1lJU6gp7wXjBwCA__1Wgng_IAN5AXorTD1dlClP9GWCsHfT?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Aom0UDD5K6GSVSlJ7PTA4s2atLPhpuVGMhMCt5PPI3_CmOe7e776Gr0mspWGbFbwV4AjOz2VEM_L3_gIiPBdO6AzzYDimNlmrOO2_8Egx8AesEJJSWpobtkvXpmRpymgt0kZie2wl03T1fqrPetOziaFZ3THT-DZgD1bwUZwPcFlR-_AcuABCkvrFXplkdtq?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/f9UMXN06yxigMHBbTRiytJJ4_lq1ZoyQPV-uUHAZ_rk9_s3zvrxF_C-d4l8k1CDMbwyJ_z7vtA4xxrNx43ojSeG91-9nbnL54v2hOyCGVi0b6up9LaQpJueLTVXbhztC6VPHIhrptNq1k1lyvGQLZx4DOB4-3QwoizFBFPjDXlQjEhYulP7O7Ske3kEs6K8Y?purpose=fullsize)

### Review Before Coding

After Claude presents its plan:

* Review the proposed approach
* Verify assumptions
* Check implementation details
* Ask follow-up questions
* Request revisions if needed

### Why This Matters

This is the best point to make adjustments because:

* No code has been written yet
* No files have been changed
* Architectural decisions are still flexible

Fixing a plan is usually much easier than fixing an implementation.

### Explore Without Planning

You can also use the Explore functionality independently when you simply want:

* A codebase summary
* Architecture explanations
* Dependency analysis
* Documentation generation

without intending to make changes.

---

# 3. Code

Once the plan looks correct, approve it and allow Claude to begin implementation.

### During the Coding Phase

Claude will:

* Edit files
* Run commands
* Update dependencies
* Execute tests
* Validate results

You can choose between:

* Approval Mode
* Auto-Accept Mode

depending on your preferred level of oversight.

---

# Coding Workflow

📷 **Image: Claude Code Executing Tasks**

![Image](https://images.openai.com/static-rsc-4/FynABmWb4gkU9Pk0p8x-cJxGk95OgSZhQ_J9kZfFmx7cyOJfEMYLoYxzFW71L3QQdEUw1ryPT1sVR0HHWe5nzfItRXUNdDhEE0AgItcQ8F600n6v5vDnuZqawkxA2HSJVv68_D2bPi3Rha4xSa9p6b4hD6lCfDIW4ZX0F7PZCAHDpF7z9HBKnv8fOq0IHK6P?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/f9UMXN06yxigMHBbTRiytJJ4_lq1ZoyQPV-uUHAZ_rk9_s3zvrxF_C-d4l8k1CDMbwyJ_z7vtA4xxrNx43ojSeG91-9nbnL54v2hOyCGVi0b6up9LaQpJueLTVXbhztC6VPHIhrptNq1k1lyvGQLZx4DOB4-3QwoizFBFPjDXlQjEhYulP7O7Ske3kEs6K8Y?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/LA_v8Fj3zYH5rffX30hy0AJPrC7XCxomJqhjq5AVl6EDG4Y7Mlz9Tvj4n8FBYggVNdeLIBC7jFl8-yZes0fObqmT0TIb92MPDh7sIfTLBWWgA4iYWK-fRPnaCO5EArSmcItoQfgFNW3jqG3BRU7YdXwmnfBzkYghfxwFh8pzQcl6xzKKHv31cxZ5dVRrbxGC?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/n_azvI9xRR3Ojcg7VlpuxI8B-pwRGtBGhBVApRuOUpEdiUVpEmLXCRAbWsJhYpYutX-2vbh9_q4qfZ6WJhSb_TQqpLt_7VAHH_2Lj3VbLLMme8esAMDTBo2USVC0qa0Y2rBQNrH7F0vup1wZLCCOGitkP0qKfzY7k1ORKiymhOMidEzAbWaYhIX1dQlIvNb2?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/JfO_2jbrW-432wVwEJYrqS8OngQMAII72txw2dJfmNiPnd_FdX9ofzleaBPvITjoHgR5sQEbTDen9ZImws0D-vQJ1K8uM_2Hya_-2G1BT7chgRVWuVPKHLsygSfd2elGFB4gDVuFcSe65oLPbKHaJnNe1VqWXN4YrPj2mbbJtOVMHvztGthihvBWBIkVNgcF?purpose=fullsize)

### Human Collaboration

Although Claude works autonomously, you may still need to:

* Clarify requirements
* Resolve edge cases
* Answer implementation questions
* Review intermediate results

The benefit of Plan Mode is that you already understand the reasoning behind the implementation when these situations arise.

---

# Tips for a Better Coding Experience

## Define Success Criteria

Claude performs best when it understands exactly what success looks like.

Instead of saying:

```text id="fvl0yj"
Improve image uploads.
```

Try:

```text id="jlwm7f"
Add WebP conversion for uploaded images, preserve image quality above 90%, and ensure processing time remains under 2 seconds per image.
```

### Benefits

* Clearer objectives
* Better decision-making
* More reliable results

---

## Add Helpful Tools

Claude becomes significantly more effective when given access to tools that support its goals.

Examples include:

* Browser automation tools
* Testing tools
* Build systems
* Deployment tools
* Documentation systems

### Example

If you're building web applications:

* Install the Claude in Chrome extension.
* Allow Claude to interact with browser tabs.
* Let it test UI behavior directly.

---

# Claude in Chrome

📷 **Image: Claude in Chrome Extension**

![Image](https://images.openai.com/static-rsc-4/nHIwMs1vP90EUHXwjGYS8X4G6wJjQRcoaW8CRmGcYBl2E0E_c9mSamVfxacD41uM916yCTp0W87xFOJUSHxCkf-EqiMvaPyg8Y4XOtA33BpqV2Y-ADercFOnjm9d0-z-v1Pat3bl8VfjddTKC9ASkDn5lfky3KzbgvFZ7vIcVllIUPpyRfTGsoT34x6dc89M?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/JB0YB2gqaVmzn3b2fP0klvFDv-fHrvoUjX1kEyQnPrUm6olYj6KiyuDbsVLcCHBFSyKFmjhhBUcAD9W8RhgU8FYJPMb-aX78Ib0gYcRankYC7GocCcOFIWAKL-HxmOP_ouuKDhCxlPl9R97ViKFXUgr2ECrEDK0i0rfxOxQP3cTMcXgyDKrpsdXhHO0sv1qJ?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/yOhH5NOXZ8IbccqB-YYsYf5l_XL2Pq5fxTaeLsTVlNJQ9sOiNcELv6gMdZG6MeUiJ7uhTRq8WMHqDki4sz7UIYUT80ure5mJtP9TSiDT3LLMOnFMioQZ_8HvStrC0ugdI9OIlT--C7bTFn9x7LsaAOvKtNa39Xx8Srq9EWFr0vQt8jQk3nkULSOKdc7omlhx?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/sqTnm9Y15njkPNgBqpmnCF-LjXxyiAMX-APToUQntlFRemdwfubDb2BRvt8mWs4lpxNWZDgXgtuXTd9_J7CYzUhXTSrQrQ7l39e2YWk53-N8j7rgQQhVFVscHIwgLUNf_vK1EuvO9lU9lByufsbf-ERdC_aGzL2_F76HUDewGiV0bmxyvoIc8_rWnMFj11U2?purpose=fullsize)

---

## Include a Test Suite

A reliable test suite is one of the most valuable tools Claude can use.

Benefits include:

* Continuous validation
* Faster troubleshooting
* Regression prevention
* Greater confidence in results

### Claude Can Help Write Tests

Claude can:

* Generate tests
* Expand coverage
* Fix failing tests
* Improve test quality

Before relying on them, verify that the tests accurately represent expected behavior.

### Avoid False Positives

Always ensure your tests:

* Fail when functionality is broken
* Pass when functionality is correct

A poor test suite can mislead both humans and AI.

---

## Save Solutions in CLAUDE.md

If Claude repeatedly encounters the same issue, ask it to document the solution.

Example:

```text id="9qkr6a"
Save this solution and future guidance in CLAUDE.md.
```

Benefits:

* Preserves project knowledge
* Reduces repeated mistakes
* Speeds up future sessions

---

# 4. Commit

After implementation is complete:

1. Test the changes yourself.
2. Verify the behavior.
3. Review the code.

Only then should you prepare the final commit.

---

# Run a Code Review

Before committing, use a dedicated code-review subagent.

### Why Use a Separate Reviewer?

The implementation agent may be biased toward its own solution.

A review agent provides:

* Fresh perspective
* Independent validation
* Additional bug detection
* Code quality feedback

---

# Code Review Workflow

📷 **Image: Claude Code Reviewer Subagent**

![Image](https://images.openai.com/static-rsc-4/7LbumXT93YEUtsDjG9U8A8BM1wgi1LVLsYr5O9mCU6yn5QU8u2jS_z4At_WSm0VuW30Yu9GDlO35VcTs2l2miUzwflKFyz633DPEfT98Se5cC3Hnh9e4yHxSY2hUyxLNGVsQOpXouy1WSM9gaRzL6rQD__DtebsJ3RunrDAKtnxno9nVkRT62qyyA9B8l3yN?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/tcoz-ipqA3R6O-CU20BRg55NX_epNdlcnVa3Q9o4UkONBG9Z8zSZizB68_aKSt3DtrjKQmV75Yqx_AyZY7gNbdCQ6_nax2jf3xl9NWUOvBCvlQywKukMTeYO3Jj7I5-SJVkd5vGR2c-EAnVM1mIewTiTtz_GP7pypvEzUOWD3rvoBUbr69u-K1PQx34crlSu?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/79TsnJScpn_30z7VI4hl-j6vbFRNJ-fTCSeaVMmHaHR78ira2CH6o02txKYnTLguVxSzSREDbNOFAQc5kQhhlWQL-Ck7nwNDXQ6qKrCidOa__zzGxhgIgcvqJ6Q31LEK93ZeW33WyBwfcWq674gkhSW9Yq8UbiF3Eg3Fi91nKICzrf7DxY-aaTpwORVP_3tx?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/JfO_2jbrW-432wVwEJYrqS8OngQMAII72txw2dJfmNiPnd_FdX9ofzleaBPvITjoHgR5sQEbTDen9ZImws0D-vQJ1K8uM_2Hya_-2G1BT7chgRVWuVPKHLsygSfd2elGFB4gDVuFcSe65oLPbKHaJnNe1VqWXN4YrPj2mbbJtOVMHvztGthihvBWBIkVNgcF?purpose=fullsize)

### Review Areas

Ask the reviewer to check:

* Bugs
* Security issues
* Performance concerns
* Readability
* Maintainability
* Edge cases

---

# Generate a Commit Message

After review:

Ask Claude to generate a commit message that matches your style.

Example:

```text id="6s0e8n"
Generate a conventional commit message for these changes.
```

Or:

```text id="hnl8l8"
Generate a commit message using my team's commit style.
```

Then:

```bash id="t48w7u"
git commit -m "your commit message"
```

Push your changes and move on to the next feature.

---

# Recap

## The Explore → Plan → Code → Commit Workflow

### Explore

* Understand the codebase
* Gather context
* Identify constraints

### Plan

* Create an implementation strategy
* Review assumptions
* Define success criteria

### Code

* Execute the plan
* Validate results
* Collaborate with Claude as needed

### Commit

* Review changes
* Run a code-review subagent
* Generate commit messages
* Push your code

Following this workflow helps Claude Code produce more reliable results, reduces unnecessary rework, and makes complex implementations easier to manage from start to finish.
