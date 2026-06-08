# Context Management

Context is Claude's working memory. Every file it reads, every command it runs, every message you send, and every tool result it receives consumes space within the context window.

Understanding how context works is one of the most important skills for using Claude Code effectively.

---

# What is the Context Window?

Think of the context window as Claude's available memory.

Everything Claude interacts with contributes to that memory, including:

* Your prompts
* Conversation history
* File contents
* Tool outputs
* Command results
* Web search results
* Planning information

Since the context window has a finite size, it becomes important to use that space efficiently.

---

# Visualizing the Context Window

📷 **Image: Context Window Visualization**

![Image](https://images.openai.com/static-rsc-4/mySvo9bG97Wuota5DFSQPmuhmUb-G-FBLZJcrdtWp3Dj7A6BE4_YaZ3lNTU5yCvCupxkqlX43dJz2LGqv2I5cdKhDmBUAFOLA_a-Q1lNUpxFghjWmBqUUPyaS85_taJSx-UW5xRBm0P-71HmoEkoVR4lmFES1RkyHKPxb8zDxSmSKrpQMYe-Zv-vmPBYHdWg?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/8SG5CgPKHeeDw4rI5j1FSTIUJ-TaARAccH76Krm_Uv6YUIh2u_HpdbcW-eUAxKXQkh6IUFIFjvLjaQl8NKXJ17BiqaKJOl1hTz0z8Q2vVRWB2EQP80BMwmQAEiVOUPkH7KO6qeOEoRjeT2ehSQrBNhZEo7MwQagYLkc9XSSqaxoXMCmYgPY8nSYrpfe7T9Cv?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/EtNIukolCVr5X7v_OFg_3m0CHGU9fAksAj25_4ktjZ32TdxQqDCf0SnXayINJT97V3w1z-BRZI02uo9XDUcSuqxPgXoQkpTVkJhEqgXE4-NPdv10sS4igjaMzX1DOlt4dSHCm4l3iVjpjNC9IME788ibrv9H4oVneA1SVlMLqmzGaSu8UiNokIH1jL5HDnf7?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/xAljIyOLeHPHBKt7Oai2owklQoZtYYzyX-H8o77Lq2L05Uz0x1JM99TCrjY5CgKrLjMIkI4jsMeG151CNRvnCsCtnExLdOZBeAV43OE1KC4qioOFsI9Zp8Ud1NcsN2Rz2FHbfHMXgn_P4F0JC0Ej_PAACDQ13iwBZLDlaMp4UaZERtoTIptvtxDmoaj052Wm?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Pyq3WemYho2ExkWHBRlSYZ-7JPQq7pjPMGnvJ6pnU8U_WokPa4d8se5c02KaxUBCBYghqDsWHDTBPKuyHDB5C1hEyRMD-0YlmQAoZVrhRU282XMxpDDyqRxyOWdQiY6NaoC4PMxR3sLDbY_J7yWtmaQOejcaugPYoDedXhDLEXZBiNTq1wFI6dhvCXFGnfMn?purpose=fullsize)

### What Consumes Context?

Every action increases context usage:

* Reading files
* Running commands
* Viewing logs
* Exploring directories
* Asking questions
* Receiving responses

The more information Claude gathers, the more context it consumes.

---

# What Happens When Context Fills Up?

As the context window approaches its limit, Claude Code automatically performs a process called **compaction**.

### What Compaction Does

Compaction:

* Summarizes important information
* Removes unnecessary details
* Discards low-value tool outputs
* Preserves key decisions and conclusions

The goal is to free up space while retaining the information most likely to be useful.

### Important Consideration

Compaction can potentially lose details.

Although Claude attempts to preserve important information, summaries are not perfect replacements for original data.

---

# Automatic Context Compaction

📷 **Image: Claude Code Compacting a Conversation**

![Image](https://images.openai.com/static-rsc-4/mIfPK89zIC5zPlHxzweQWDkOIXMSas9MvKqpL-jRrO2uufl2bav3_F1SIQihNNWlkzrlpNTLAZa4CQBM4DdxUEh2GLb44dhO68KXTEZvsKe21SmQ95OvcUkhH4EZjDVrFYmsp7w9HNevtWOsyCCOhLgrTXRbO6M-hAJcs8NCaTsJvbMCdWv-mQy9-Qy-usB9?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/CqEybgauE2Z1QTUe5e5j9dHNd47YXetCFSnZBe9v6eKjxRXobOUuW0Q4OGmHOmwubkhYugEX6ksQFNBD71h659BZcK6lpd2XMlOJ0lBUkesDEbfTHbKtZ77WU-bRCwJykH6cftl2mjX99ohyyic88et_jc5lrKmVMXxEH_W5jLUi60S2N3utF5CrNKxsCVgt?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/cWsk5_70ESspmAQP3HX_E9f6lZF5XzlA8flRtbaHbiPOsn9x5x90oZ_klsZ1wtU8sU2y75DNUw7xHfWIs3Ygqqv3h6a9rWACLKr3XD1tf3i3lrsS5kOAAmPFANg9FJEgzydvARliTYvVdaeOiFiPXM8gDNvu1ftab6BuZ6cbxPZ6URow9UWyLBmrggClgyvn?purpose=fullsize)

---

# Context Management Commands

Claude Code provides several commands for managing context manually.

---

# /compact Command

The `/compact` command manually compacts the current conversation.

### Usage

```text id="6lb4t8"
/compact
```

### What It Does

* Summarizes previous work
* Reduces context usage
* Retains key information
* Frees space for future tasks

### When to Use It

Use `/compact` when:

* You're approaching the context limit.
* You're still working on the same feature.
* You need additional context space.
* You want to preserve important project history.

### Benefits

* Keeps work moving forward.
* Reduces memory pressure.
* Maintains feature-specific context.

---

# Compact Command Example

📷 **Image: /compact Command in Claude Code**

![Image](https://images.openai.com/static-rsc-4/CqEybgauE2Z1QTUe5e5j9dHNd47YXetCFSnZBe9v6eKjxRXobOUuW0Q4OGmHOmwubkhYugEX6ksQFNBD71h659BZcK6lpd2XMlOJ0lBUkesDEbfTHbKtZ77WU-bRCwJykH6cftl2mjX99ohyyic88et_jc5lrKmVMXxEH_W5jLUi60S2N3utF5CrNKxsCVgt?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/cdtcRE-WDJDyddIAU57TArgxUejBnH7ivIQSQDWRELXTVB26TZwKmh0gGzyeQuOMDaj1uvQ-p3Q5vErCPTXqB_A7KjUdp46mmSQZhGelTq3DaE994RgSS7kBl8JpfNm1izSeGO_2VEEID9fayttlFe4e-3tyA74qm3YYsLpnM20fyBjmZ_PnFHM9tXwDimf7?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/JmAcBLfqb4rXXS5Ln3oHr4CABd0_ZlnVajQ7jdR7TMiP2bcmIyl-jBuLVUSU9zPPdXZ03hT-rB29P7g0U3_HwGVfghjtuT1y_X7LB1K9hYXeQEOwWxZyJkkTgAv1ULGIxWviAPe399Mv4YlaSrMph0A-f06dpmrOjfN31zwfd7VSwxG3I0D_0xqQ_zIBxDwJ?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/mIfPK89zIC5zPlHxzweQWDkOIXMSas9MvKqpL-jRrO2uufl2bav3_F1SIQihNNWlkzrlpNTLAZa4CQBM4DdxUEh2GLb44dhO68KXTEZvsKe21SmQ95OvcUkhH4EZjDVrFYmsp7w9HNevtWOsyCCOhLgrTXRbO6M-hAJcs8NCaTsJvbMCdWv-mQy9-Qy-usB9?purpose=fullsize)

---

# /clear Command

The `/clear` command starts a completely fresh session.

### Usage

```text id="knpw4s"
/clear
```

### What It Does

* Removes conversation history
* Clears temporary memory
* Resets context usage
* Starts a new session

### When to Use It

Use `/clear` when:

* Starting a new feature
* Switching projects
* Beginning unrelated work
* Removing previous-session bias

### Why It Matters

Old conversations can influence future decisions.

Starting fresh helps Claude focus exclusively on the new task.

---

# Clear Command Example

📷 **Image: Starting a Fresh Session**

![Image](https://images.openai.com/static-rsc-4/LbM_6Fwlb19V8rHSinZvRTh01zQRFg5RdDs5NBB0RiBinL-iCQHy5UqFW_Pq6qSYkf2oeZ7S8ep5zjzW2z6NOtw03WSSmlml8iJSl6BqDq-rm9CweTKtgyT_EXzxngj342dfGcfevfFPL3xtwrdNOg_Lw7V9QI28JQN4Y8CreSKC7_lkAiexa9aDZo4RPTOf?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/AAhblU1YaIEyMy3bvUOOxFrP_BBhEzgAJ80jA80aAek_vJMhvBGtl3EcezVRzlo0YW2UxuxwN6W5JLdnQarFpX8BfuR2yRwbXDZ4OXmQNDAxv9Bn0MFDbZcVuj4_haHtdf3h4sdfZILdiTsRg5fKXJAWOF2CCrVCKCI4_hhSLTv7mgRVzCywtxwjZVXJQH5v?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/tkW0x2dLL8Hi4MbTWX53j62bNyoY1jqXQTsMdHN0falgOGG11C7P4-W9l0_b2ENNT2jWXh0-Jc4a06H6PepI4vXj8jET0sZBzzuPN0oNRnOV9ziRhQFrroMD-pdG1xMeNl9_dBu2QHCOj_FEyz5qimvWr6NbFO36rnDlZgScoaI-O916GCcVf2W3Dc7Sxdtp?purpose=fullsize)

---

# /context Command

The `/context` command helps you inspect current context usage.

### Usage

```text id="x4ngy8"
/context
```

### What You'll See

Claude provides:

* Overall context usage
* Memory consumption breakdown
* Largest context consumers
* Visual usage indicators

### Why Use It?

The `/context` command helps answer:

* How much context is left?
* What's consuming memory?
* Should I compact the session?
* Do I need to start fresh?

---

# Context Analysis Dashboard

📷 **Image: Context Usage Breakdown**

![Image](https://images.openai.com/static-rsc-4/lldVnzYqSo2LGM8m9vsev1YLXIz4TMK9Dp6KM4SNI4B-4MiIXolY3G2w5bF-u2_T14tznxKMcKuze1njVUxl4g33-azzoW-JSAdQRBQT2ErGbYKYg95QRNP9ffBR2viaROd2JTjfFUIWEN9HSwcpFnvNzVkeElCaGA40NzUpwdw-lBhYEFDy1b3QBmWojGH5?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/uT2RR7zPf5YHai_C6GWaTibyWgMK3ssVamuinTuqmqYjSe9WftgytmvMHGJ6OwurX8qfgYz10XN_Qtls1lkX7Buy-1kPigCU9XmNhISdHnDbOZF608YLVlRC9cfBjVVbb3TViOiMpPclASYNYVuqTTt5Yo-UuKzNKz33JGD8wtCdthXOgLO0O5WgFbFd-YjK?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/1ZEKzvUmtNzpIQIyfrmhe-rNdxw8zx-7e8jIZqQewJiSX5_5WXKWD12cWQcfKBJ_d-ViB-jbD4MrIMo8YeBts05Hjv05GMUyZfh0Yq2sBnXCSd2mTB5pTbmE7dfAXj-29-aFoS7xamYkkW40EuOk7oyXFnhJMfu7cIwjY_fcNmKJMgo2lLHxCr-gBH2djXBF?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Nxy6eVv6zH8hwf-77C7WLngqtd0pgSKUBqAajwFt-r58YGZlHS-xRi-WDF5hxg5H56MbGMA_AJluH5jVbwQkk1-Ksd7F5tbcwFcbsQbjny763yzOZ8q7ACUGepZpep53Sq9YZPxOh6O4NBscxdelBTBRQWqx3UEgIpQc3RMxD2nQlJdf8OdMy1AT3vK_AQbS?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/7PnDAOjEBCtxtpllQpNgDbE_GwHizGG8rfxVER8pnanHM0pMv3aOLopmHhhg2U-MzVmqKhuSG_yyQKi2Y6R__mwDLpujdkzlDaELSs6FKlpb1dXAodAuvZkAQkOgMZiyIATIXrkjIvXKW9qQEGATxTLujqxmaEJbHzCyh3U8AKIrGNCEw0SschpFmMPJmzqD?purpose=fullsize)

---

# When to Use Each Command

## Use /compact When

You're:

* Working on the same feature
* Near the context limit
* Continuing existing work
* Trying to preserve project knowledge

### Goal

Keep relevant information while freeing space.

---

## Use /clear When

You're:

* Starting a new feature
* Beginning a new project
* Switching topics entirely
* Avoiding previous-session bias

### Goal

Start with a clean slate.

---

# Long-Term Memory with CLAUDE.md

Some information should persist across sessions.

Instead of relying on conversation history, store important information in:

```text id="t2f7yu"
CLAUDE.md
```

### Examples

Store:

* Project architecture
* Important commands
* Coding standards
* Development workflows
* Team conventions
* Known issues

This prevents Claude from rediscovering the same information repeatedly.

---

# CLAUDE.md Example

📷 **Image: CLAUDE.md Project Instructions**

![Image](https://images.openai.com/static-rsc-4/_FUCQxFfJDA7FV09_OPQgZxO085jmuy4tVUrlYau0ngDGgIgxkyRSFPJEnua5YOih_neskEgVPnhu-WUaDQb5xJ9gn_U4SWxoN7jfXUgh-GLvSVNyLds-DtCC9R-1PbCgukPIh02JnFdooDNoZ0jmw2SWPYIsp8_xZLLix_TKA5eTqpWaYLXy1PvWWh1qNUL?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/I07M7J8vODx6rH7920qXXNaabwZq0157UVELMeJvET7gC0Kc2gQxsRypBI9kQNtfxCV1ZUxpm_iixFyIECpU3EU83zAJIAQHOWPZhkdA_NOcXYrm5J2uqkn22FfRvRoNikuaim58V-7K55J1czZk-XefICGQE6YggQm5ckgL-M9F18Cx13nog-OqGy4gjtt6?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/HzHZ6mrWyJmZFxUk6xLDKtAD9-dJMgPt0XzbLnYIFfiO7Y9dER1vG3xsleP38OtYXlxLGZ_FcfQYjZyIDy5AXpE7CpinzLUYOqNkp_mIEq-Q-Tf0D-9jbRPkdqplM7FuI6mZqH2c1bfzJsxrX9Ar6ZGJhyC7da6Wd8vubdJ0pJ7s-H5o58Z5pjvwO-BoANqB?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/xC5NgjcMrvlIkrDRUEgk5tmY4iaISB2WcpYDlDAhxlvBlYsaWYndaOaKc8ZcAUhHzLdTZWB7RIVOaoN1HfnG6gQjBwBju86uWWD2x_2vPUzF3UWwmUHOTLhCkBNk_ZErs9KN3ghwujSiD6HP-iiQMVBjiADj2Yz6vUcSrqC9pVJSQot8r7FkvwnL4Vbv2LaF?purpose=fullsize)

---

# Tips for Saving Context Space

## 1. Be Specific

Many users think shorter prompts save context.

In reality, vague prompts often consume more context.

### Example of a Vague Prompt

```text id="f5a6z8"
Improve image uploads.
```

Claude may need to:

* Explore the project
* Inspect multiple files
* Infer requirements
* Ask additional questions

All of this consumes context.

### Better Prompt

```text id="6pzy2u"
Add automatic WebP conversion during image upload while preserving transparency and maintaining image quality above 90%.
```

This gives Claude a clear objective immediately.

### Result

* Less exploration
* Less guessing
* Lower context usage
* Faster execution

---

## 2. Manage MCP Servers

MCP (Model Context Protocol) servers can consume context automatically.

### Why?

By default, MCP servers load:

* Available tools
* Tool descriptions
* Capabilities

into Claude's context.

### Recommendation

Disable MCP servers that:

* Aren't relevant to the current project
* Aren't being actively used
* Add unnecessary complexity

### Alternative: Skills

Skills offer similar functionality while avoiding large upfront context costs.

Benefits include:

* Smaller memory footprint
* Faster startup
* Better context efficiency

---

## 3. Use Subagents

Subagents are one of the most effective ways to conserve context.

### What Are Subagents?

Subagents:

* Run independently
* Have separate context windows
* Perform focused tasks
* Return summarized results

### Example

Instead of asking the main agent:

```text id="86lmxz"
Find every authentication endpoint in the project.
```

Use a subagent.

The subagent:

1. Searches the codebase.
2. Collects findings.
3. Returns a concise summary.

### Benefit

Only the summary enters your primary context window.

This dramatically reduces context consumption.

---

# Why Subagents Matter

📷 **Image: Main Agent and Subagent Workflow**

![Image](https://images.openai.com/static-rsc-4/l5RVGC8FgM82mYHMVo1uatrGXkR6Amsm3p6VjSu2j_UBLn0O6WsTDbDXReUlrBLVuMJ7T_FLRAZRlTMDjG0FK79_k8rYWcKpd824g5HbD2iBZGi-BHo4UFpHA2-Ke4ac6KfqiHjdvnowhDDSTe41sS9Lw9NXSOfcdfoVhJndwMYxIxGTmYuW4SVyW_MvZqHL?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Qs5C6fxaDlZTC0I2AQvOt63CBK7fZI95DDxEo4JIDT4pfI3mF3ZcfSbYPyVyOAHwdu4rHQDOu-IfSPibb08PerO-MY4AEAbnapdxoXNqNRrbFNGITorxdXd-83UBAULmiQOC5Hysq3X_DQ6cUTappG8UX1c2v2LWMiiR-brKLMcakNFe2W-WOnS7l10TA_wX?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/wWA6VLOSxpFfE0tj1_07e6lZUcEVcBmstQnDPS5esgNgNvGVB-yaTkDIfqfZsq2QJWPFSd_MrKXZ5ZDHXm5tG8RFK7ACNRkv9bVOTA6VhMk92dyPplEBK7Amv56d_YsLuQdqeyTcpRKBLvuegJWk7Mfw9Gga8AgfvdtFyB6tRl_r1rRK94U2SkQYYli9iUgy?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/I8i4N6WQeMO4z_CyiOyJPoYNbCkIF--kvreHmApsjPLM76z6LiZilxufUd03rgj1tPLMvjfkZ2fPc7BgTbh8OSkYv3HuXwcB21InC6iF2PhetTtGIbiO1d2AaWgI4UNRHONtn7lgW_5N_xbWSlCdE5iWShvnT8laN1MlRQA6FsNb7kmSvKtKfn_pG92JvTZC?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/6r4dBk_eo_pFW67NOopqwlZz0VniFMr8as7l48KpuBS7Hg1oD3pke25DdEvZdDYMBIBUAhpSSxqr6ZKGJCakDdKwCUMSs-SHOBMWTcGBdC2Hph5k9LTdjJA_oblZJprkXNsiXFheXDEbZMzK-SPqp-pA48qAEmlqHefc4sriZvwSbQvtQpPX-mZ8RgC8q-r1?purpose=fullsize)

---

# Recap

## Key Context Management Commands

### /compact

* Summarizes previous work
* Frees context space
* Preserves important information

### /clear

* Removes conversation history
* Starts a fresh session
* Eliminates prior-session bias

### /context

* Displays context usage
* Shows memory breakdown
* Helps identify context-heavy activities

---

## Best Practices for Managing Context

To maximize Claude Code's effectiveness:

* Be specific with prompts.
* Monitor context usage regularly.
* Use `/compact` when continuing long tasks.
* Use `/clear` when starting something new.
* Store persistent project knowledge in `CLAUDE.md`.
* Disable unnecessary MCP servers.
* Delegate research tasks to subagents.

Effective context management allows Claude Code to remain focused, efficient, and capable of handling larger and more complex development workflows.
