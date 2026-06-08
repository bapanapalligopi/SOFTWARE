# Your First Prompt

You interact with Claude Code much like you would with any AI assistant. However, understanding a few key concepts can help you work more efficiently and maintain control over what Claude does.

---

# Auto-Accept vs. Approval Mode

Claude Code gives you control over how changes are applied to your project.

You can switch between modes by pressing:

```text
Shift + Tab
```

### Approval Mode

In Approval Mode:

* Claude asks for permission before editing files.
* Claude asks for permission before running commands.
* You review each action before it happens.

This mode provides the highest level of oversight.

### Auto-Accept Mode

In Auto-Accept Mode:

* File changes are automatically approved.
* Shell commands still require your permission.
* Claude can move faster through coding tasks.

This mode reduces interruptions while still keeping command execution under your control.

### Which Mode Should You Use?

There is no right or wrong choice.

Choose the mode that best matches your comfort level:

* Use **Approval Mode** if you want to review every action.
* Use **Auto-Accept Mode** if you're comfortable allowing automatic file edits.

---

# Auto-Accept Mode Example

📷 **Image: Claude Code Working in Auto-Accept Mode**

![Image](https://images.openai.com/static-rsc-4/4FZzoZzCT8XVTSCMxAjex_zFcKYrKgXB9HwNMu5C9ALj2h48zFAOuhuBv007s9E1J4eSzo5XJA1Sa8UQXdZEYMHcivRXJ5aZRtBK70ELF57Uq3EqKJXyptUABMJsxfK8Jr_3IaSpXkY0HGUF_znLwyd8oDOtOUdRYFFnZdZCKh8-rsXqSBaAIPhB280KMxpJ?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/INLHTX7HT0ttWzHWNS0csfEX1N-UE5l-0UTk7yUz_w8kXzFNTQSePM-S_t07Niq32M_RsVTRnC6NPZqhKCR65kDTk8uwhCzXSe-XEWwLZrjFIRNWD9g5DFVC0KBNNZmFats6gpwo3L6EPRFvAg-4mVIPTpRNnOHHBmuZDu-EkuduTXfeSx1ySIhnADbZbrPy?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/1bXUoUuUhjMeHbhKeqnu8S7Ry5toq_tq2tyf-xDEIeyQyqVnUD6y5CqfUENlYUJjLezF5YWm_O1AF9tyBPVioQgbQf_1FjbUtTO6bFamersBUvdCu6UyCR8jpy-jYdFZ_aNpGzz5tcc-FaCpdLE5EFw7c2_zxU4tqmkN5tahy1L4EVx-YKZguDRVupAvMuIP?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/RNx3iJ70Mf4Vjbso-VKw5Xk8GcqmRUjvv6F79-A9k43I2YKW-KYtsVII3pq6u-DEjuxbiNOhCnkFMTAANC4404l-ES5OTxh5XOAZMmidD22aLAqnPP8JMLPy5fUbHDe4TDdk5779uFa96CpXPlrsUsEAL3xO2-ZDe4rwpU41L34D6v-ifclx_9Yrfp82qNOC?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/7XHfhAIXI9j6nxOqGMWZ02cObYYzTTprshORwKGqwwLkpoYXPnjw_u0G72M02lksLWQWYfH0zroMXAJzIeZ81De_cdS4Zb1VgmvmJkm7l8KjwdlNmzpUJnR4Ssa1Ud5fO5xS4iPJltURzJdqLCDXVBTPk8AVe2mEEWgA7Wp1Gp3pl-xtpV5j8DDqvi3KXHxN?purpose=fullsize)

---

# Plan Mode

Another option available in the Shift + Tab menu is **Plan Mode**.

Plan Mode allows Claude Code to:

* Analyze your codebase
* Research implementation approaches
* Ask clarifying questions
* Build a detailed execution plan

Importantly:

* Plan Mode only uses read-only tools.
* No files are modified.
* No commands are executed that change your project.

### Why Use Plan Mode?

Plan Mode is especially useful for:

* Large refactors
* New feature implementation
* Architecture changes
* Code reviews
* Risk-sensitive projects

Instead of immediately making changes, Claude first explains what it plans to do.

---

# Plan Mode Example

📷 **Image: Claude Code in Plan Mode**

![Image](https://images.openai.com/static-rsc-4/INLHTX7HT0ttWzHWNS0csfEX1N-UE5l-0UTk7yUz_w8kXzFNTQSePM-S_t07Niq32M_RsVTRnC6NPZqhKCR65kDTk8uwhCzXSe-XEWwLZrjFIRNWD9g5DFVC0KBNNZmFats6gpwo3L6EPRFvAg-4mVIPTpRNnOHHBmuZDu-EkuduTXfeSx1ySIhnADbZbrPy?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/meipzg_0pn4N7U1hW31Lx3oDEis5JcCMXoI6GzPsDjjRt4qeyLjkCZhpI6jAypjBCAkOx83NM4eO7bW-XCVD6yQtOql7endkZZMh8aqy4hPkoBXVaNbyllz7hRKd2V9wue9NdO3LluFyVdIb1KlAjPFS1roWEVyBZ9MEoEZmt34qI7eIKL945dC92w2tnK7M?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/HvWL991YpjVfJ_FL50BKwhxfOGrnhS7T-OuAJbBNXovAt4i7zs47THeXVbPZlKO-LqQs-wSRBtcnQOSEhMI1wn6kuxWvh-spXBujY6esrAxKpgHpe-HLFytlvs3R4zhzvVEPvgzQGMutMhnR_ZPyuZFVw39KuYiDMEv2PGJzaoIXp_qwkWMmLjRUs-wmJsoE?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/muiS0AlL-3IvydD9_7DYnrY1uJ4N7NNzqohCv3NExiFWjrviDWi3L56REWfxK_qI6S-noNhmNTfo3_euQHml7ALFwHHCEEOZPnnOat68zYdUndHDaVrU2-KnZ0rmGjirvFfUYmTSBwwhSh7pENUG8Y_xcTpJunZyaTd-eupdCawiysu1MGgtYoAHWCEAgmEF?purpose=fullsize)

---

# Example: Add a Dark Mode Toggle

Let's walk through a real-world example.

### Step 1: Open Your Project

Navigate to the root directory of your application and launch Claude Code:

```bash
claude
```

### Step 2: Enable Plan Mode

Press:

```text
Shift + Tab
```

until Plan Mode is active.

### Step 3: Enter Your Prompt

Example prompt:

```text
My app needs a dark mode implemented across the entire app. Can you create a toggle switch on the header that allows a user to toggle between light mode and dark mode? I need you to find a good contrast color that works based on my existing light theme.
```

### Step 4: Review the Plan

Claude will:

* Inspect your codebase
* Analyze your current theme
* Determine implementation requirements
* Ask follow-up questions if necessary
* Present a detailed execution plan

### Step 5: Approve the Plan

After reviewing the proposed solution:

* Accept the plan if it looks correct.
* Allow Claude to begin implementation.
* Review approvals as Claude works through each step.

### Step 6: Review the Results

When finished, you can see:

* What files were modified
* What commands were executed
* Why specific decisions were made
* How Claude reached its conclusions

---

# Writing Effective Prompts

To get the best results from Claude Code:

### Be Specific

Instead of:

```text
Add dark mode.
```

Try:

```text
Add a dark mode toggle to the header, persist the user's preference in local storage, and ensure all components follow the selected theme.
```

### Include Constraints

Mention:

* Frameworks being used
* Design requirements
* Coding standards
* Performance considerations

### Describe the Desired Outcome

Focus on:

* What you want built
* How users should interact with it
* Any requirements or limitations

The more context you provide, the better Claude can plan and execute.

---

# Recap

### Key Takeaways

When using Claude Code:

* Be as descriptive as possible with your prompts.
* Use **Approval Mode** if you want full control over every action.
* Use **Auto-Accept Mode** if you're comfortable with automatic file edits.
* Use **Plan Mode** to safely explore and design complex implementations before making changes.

### Why Plan Mode Matters

Plan Mode allows Claude to:

* Understand your codebase
* Ask clarifying questions
* Create a detailed implementation strategy
* Avoid making changes until you're ready

This makes it one of the most powerful ways to handle larger features, refactors, and code reviews while staying fully informed throughout the process.
