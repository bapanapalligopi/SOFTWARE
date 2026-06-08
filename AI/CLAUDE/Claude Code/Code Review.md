# Code Review

Claude Code includes several built-in features that help streamline your Git workflow. From automated reviews to pull request creation and session recovery, these tools can significantly reduce the manual effort involved in shipping code.

---

# Review with a Subagent

One of the best practices before opening a pull request is to perform a code review using a dedicated subagent.

### Why Use a Subagent?

A subagent operates with:

* Its own context window
* Independent reasoning
* No knowledge of the implementation history

Because it didn't write the code, it can review the changes more objectively.

### Benefits

A review subagent can help identify:

* Bugs
* Edge cases
* Security concerns
* Performance issues
* Code quality problems
* Maintainability concerns

This makes it an excellent final checkpoint before pushing changes.

---

# Code Review Workflow

📷 **Image: Code Reviewer Subagent Reviewing Changes**

![Image](https://images.openai.com/static-rsc-4/Ya4VJQzzXAuMPWORXD6IyPd_sIGEAr4lNR89Jxx2nLorBjOH5Gru53jgG-FVkkx6jA66a6vAIJnBF3s3Kx5M0Hg0naT0WhHS6qdgc5f27JiANDtvohnMxm8J0Whlw6BMuBHTlsKKBmeuIJ_wJv4tCqBw2GVnkOtx6KUV3VPq-i_JkOOdq3p9eC8SGcDr-Ddo?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/T-7aemcU_WgovWDffeXciroG5DXQ8yPsD99o3_cKpu2bQ-rdCsZDeyS3XZfmgP0A79Eq8vxXIjqjuI0xCbZIhtWMJi18zGL88kZa8dxI5p-9-C2t8fdeH3d9egiLopjGt6LBmEoEF-3ylHa41WAur0Tr4xaX5sP9SLg5N2fAEn-ZEMeJHIw-puaV18iZMN_u?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/9tIBTKyNHgdCwaktPWmciJAMEe529lc7LPUsNs0uK3elUahf0Sy6sqSEIwQwL4etnmXqsJcQx9p2JRSSpiaedZbkunYngwd9aFzlYae2qK9AFLb3MfAK9u061wAIbrepLcNEqgMAX8x4ubZL7GwrS9Q4CQK5zW9yFffxA2pKwunUivX9hgMkC3LMnmJ2LXy2?purpose=fullsize)

### Recommended Configuration

When creating a code-reviewer subagent:

#### Use Read-Only Tools

The reviewer should:

* Read files
* Analyze changes
* Inspect diffs
* Run reviews

The reviewer should **not**:

* Edit files
* Modify code
* Apply fixes automatically

### Why Read-Only?

A reviewer should focus on:

* Finding issues
* Explaining concerns
* Suggesting improvements

rather than changing the implementation itself.

---

# Team Consistency

To ensure everyone follows the same review process:

### Check the Configuration into Your Repository

Store the reviewer configuration in version control.

Benefits include:

* Consistent reviews
* Shared review standards
* Easier onboarding
* Predictable feedback quality

This allows every team member to use the same reviewer setup.

---

# The /commit-push-pr Skill

Claude Code includes a workflow automation skill called:

```text id="1pl2zd"
/commit-push-pr
```

This skill combines multiple Git operations into a single workflow.

### Instead of Manually Running

```bash id="bxs3hj"
git add .
git commit
git push
gh pr create
```

Claude can handle the process automatically.

---

# What the Skill Does

The `/commit-push-pr` skill can:

### Create a Commit

* Review the changes
* Generate an appropriate commit message
* Create the commit

### Push the Branch

* Push changes to the remote repository
* Handle the branch update

### Create a Pull Request

* Generate a PR title
* Generate a PR description
* Open the pull request

All from a single command.

---

# Automated Git Workflow

📷 **Image: Commit → Push → Pull Request Automation**

![Image](https://images.openai.com/static-rsc-4/pybKtISeJMSbAwbaWfRT0Ey2MNci7T_IUTAm0-SuhwYjZFuwMLV3vUehew0DVPhusUC1uoKLrgVJdWIw_3ZvfYzy3TYgNTOD3q-wtDV8x-3_D4qSdoTK73gBIrl1ISRUyoE6rc76xIE6Wy1C0iSU_M7uPxkF_4_YZCMEMwC86xRriOzWDSNRtAX01rvDkpe9?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/XTZWlyDmD9Scq6j1G92Tym7jqnoYBtrLEBR6k5hS-tyxlLO-OZPoPLEvOhPagbZ6ya7s_K6vCB2IPMrFhoMw1HhN2ZDhFEUdHyRP8O58map3NQjSXX3ZgVgbe-_ByB4LZKmpzp1pZO7K3PWR8mCIdlepmUv1tiK2zJTYXiHSGYHVHSXsasigrAX_KKYlsUUw?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/qqaNdJdgdEadWCIvo8Rg7mQva1NSkn3zhjzJ_5ezcWYPdJ4zArgyng5TA7F_A00e18NPHSU2N9p_ImsKSu35miv2WRjKDTIioPgajeF8xM0NgMySGPYJC3DC-b00xDIruSP8DJQfdUGNPijFVASb83E66z8lDmWyUILKdV_V2AFCiroSznx-zzsfRjoz741B?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/l3DH9W9uaQCp-oVceqO-vsIRxv6SngZNd275MPLcjSUn3hxxkOYqjBiTxhrNG6EsimEH7oB6st2KtQs77rNJR1dlRRbQXGvyj4kgxwDFrnbzagWlgQJSjwqC15g9WuN0Hj_Mmp54CINyt2suZPbRIvyDelcynaOClw7pIelkchg5iXJGTlmqXaw1MGOQRnk0?purpose=fullsize)

---

# Slack Integration

If your environment includes:

* A Slack MCP server
* Slack channels configured in `CLAUDE.md`

Claude can automatically:

* Post the PR link
* Notify the team
* Share the review request

### Benefits

This removes another manual step from the deployment workflow.

Instead of:

1. Creating a PR
2. Copying the URL
3. Opening Slack
4. Sending a message

Claude can do it automatically.

---

# Session Linking with --from-pr

One of Claude Code's most useful workflow features is PR session recovery.

### The Problem

You create a PR and later need to:

* Address review comments
* Fix a failing build
* Resolve merge conflicts
* Add requested changes

You may not remember the full context of the original session.

---

# Resuming Work

Use:

```bash id="rnx8b4"
claude --from-pr <PR_NUMBER>
```

Example:

```bash id="pw1d4v"
claude --from-pr 123
```

### What Happens?

Claude:

* Locates the linked pull request
* Retrieves associated session information
* Restores the working context
* Continues from where you left off

This allows you to resume work without rebuilding context manually.

---

# Session Recovery Workflow

📷 **Image: Resuming a PR Session**

![Image](https://images.openai.com/static-rsc-4/l3DH9W9uaQCp-oVceqO-vsIRxv6SngZNd275MPLcjSUn3hxxkOYqjBiTxhrNG6EsimEH7oB6st2KtQs77rNJR1dlRRbQXGvyj4kgxwDFrnbzagWlgQJSjwqC15g9WuN0Hj_Mmp54CINyt2suZPbRIvyDelcynaOClw7pIelkchg5iXJGTlmqXaw1MGOQRnk0?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/UVkNKXpWiyA9dKHqJTmBAspBaTCflDZZxw758QsK_uQNEK3Lrh5X2-Q0a8SQsp2sFOU4_hka8bnWYAK8lx3X5GtjOBf06aB1hm910-vfj78vYi_Mf-nexcy2sdcGJ_-p-RAlnehXpk9SySIpIZOu48vjhnOVx5rIeW5lFBnrwgJVzHrEaLL9Ia5np6caX4SV?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/4gqyPhCZ6Dm_3pN0l-xsRzF-ewhdVmW3Dc_xc_CbyI4ameJKnHWmtPt326BhAMgc1tMwBZF8Bt1Qw61e0iLRIguIqs2QONw6bLZrsrdxIJEf3u1bxaYLitBwc2j42IhUdqua6LZvWxD_HCrODMamU2pWPq0Aw2AvnzfOW-2b7E-qxreJ2MdCFE2H3h1jOtro?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/HLLJq3VI014qciDvy7JsxDdYScNQpH0w911X8gc94A0HIAvTICX7bW5Y-FEmMcs79KA1r5ZAzZpnU0qubak7kLCUdADx3X6wNIGwXTxluvNuHdNC2gy5hjjERPj1VDasHdD0jURZJojs3Wy4ErM5aYXw5q-eI46KdIv5ImjTJW9EqyEFTg_OtczwPDPcMayl?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/k_k-raw-3VeyDKZI9jQXmSsSURa_ZNMQpF7vfI4tYvnqBkjfjfAWkBlPLZoSsoZ74Vh0c6K7uNcgwNxPaiPzPCYS6-A6BhbYGuiIpb523hhplTZgxHNU9dBfOHW-6SziEiZEBdjvqJ_-AHG_F4jB8R6YyaluW4IdtceNTx9j-U698Goi07TaZcEi-lM-DNRg?purpose=fullsize)

---

# When to Use --from-pr

This feature is especially useful when:

### Code Review Feedback Arrives

Example:

```text id="y9rqdx"
Please simplify this function.
```

Instead of starting a new session, resume the existing one.

### CI/CD Fails

Example:

```text id="v0zklg"
Unit tests failed after merge.
```

Claude can continue working with the context of the original implementation.

### Follow-Up Work Is Needed

Example:

```text id="j1l0ra"
Can you also support SVG uploads?
```

The existing PR context helps Claude understand the feature more quickly.

---

# Recommended Code Review Workflow

## Step 1: Complete the Implementation

Allow Claude to finish the planned work.

### Verify Functionality

* Run tests
* Validate behavior
* Review changes yourself

---

## Step 2: Run a Review Subagent

Ask a read-only reviewer to:

* Analyze the code
* Check for bugs
* Review architecture
* Suggest improvements

---

## Step 3: Address Findings

Resolve:

* Bugs
* Performance concerns
* Security issues
* Maintainability problems

---

## Step 4: Create the PR

Run:

```text id="4k2nqa"
/commit-push-pr
```

Claude can:

* Commit
* Push
* Open the pull request

---

## Step 5: Resume if Necessary

If additional work is required:

```bash id="p5l2ya"
claude --from-pr <PR_NUMBER>
```

Continue where you left off.

---

# Recap

## Use a Review Subagent

Before pushing:

* Run an independent code review.
* Use read-only permissions.
* Let the reviewer identify issues without modifying code.

---

## Use /commit-push-pr

This skill automates:

* Commit creation
* Branch push
* Pull request generation

reducing repetitive Git operations.

---

## Use --from-pr

When revisiting a pull request:

```bash id="m3b7qf"
claude --from-pr <PR_NUMBER>
```

This restores the original working context and allows Claude to continue helping without starting from scratch.

---

# Key Takeaway

A strong Claude Code workflow looks like this:

**Implement → Test → Review → Commit → Push → Create PR → Resume When Needed**

Using review subagents, automated PR workflows, and session recovery can eliminate much of the friction involved in day-to-day software development while improving code quality and consistency.
