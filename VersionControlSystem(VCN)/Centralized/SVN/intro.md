## What is a Version Control System (VCS)?

A Version Control System (VCS) is a software tool that helps developers track and manage changes made to source code or files over time.

It records different versions of a project so developers can:

- Track changes made to the code.
- Restore previous versions if something goes wrong.
- Work together with other developers.
- Identify who made changes and when.
- Maintain a history of the project.

Example: Imagine you are writing a project. You complete version 1 today, make some changes tomorrow (version 2), and add new features later (version 3). A version control system keeps track of all these versions.

## Types of Version Control Systems

There are mainly 3 types of Version Control Systems.

### 1. Local Version Control System (LVCS)

[Git Version Control](https://images.openai.com/static-rsc-4/YLBV1xVrHSkKYOgd4W6ic7ZEQguHozWqaYOvFLQeElHc87mnCwsv3ajvYioc7gyjFSoRWjY-yx_vmV-piO6AlOL_fkffrMm7ZSGJf7P10eLIy1s1PFk73uUwfmZHSNIZQ92J6J3O_YqtsNup73cGoI4bCOdZgEB59DryjrlqD7I?purpose=inline)

[tutorialspoint.com](https://www.tutorialspoint.com/git/git-version-control.htm?utm_source=chatgpt.com)

- It stores all versions of files on a single computer.
- Changes are tracked locally.
- It is useful for individual developers.
- Other developers cannot easily access the version history.

Example: RCS (Revision Control System).

### 2. Centralized Version Control System (CVCS)

[What is Version Control? A Beginner-Friendly Explanation](https://images.openai.com/static-rsc-4/inP0QHAekk6veCvEezUsUf3xguaxGblwSY47NSxdQeR2WgN__aNyEJNIBC-UDJ-Qmdxq7mCR68ljTrYuzr4gyXUrHcTxXeeQmMdoLYtu9xQ-TmyYPSz0WABNtjYKntzVjxJb2Lx5v1xedN-5zBpJiUwxARxiTVqkAnZrKBFhjAU?purpose=inline)

[filmora.wondershare.com](https://filmora.wondershare.com/video-editing-workflow/what-is-version-control.html?utm_source=chatgpt.com)

- It uses one central server to store all project files and their versions.
- Multiple developers connect to the central server.
- Developers can check out files, make changes, and commit updates.
- If the central server fails, developers may not be able to access the version history.

Examples:

- SVN (Subversion)
- CVS (Concurrent Versions System)
- Perforce

### 3. Distributed Version Control System (DVCS)

[Git là gì? Tổng hợp 14 lệnh Git cơ bản nhất cho lập trình viên](https://images.openai.com/static-rsc-4/PlN67-odra_UadY5obJxaoEN9vFpmW98Vv_b8JqNq-ui2j7-gIG6GG2lgQdm7Q4wYuvSL0airJ0H9R8PKIFWERFaDgYtSQwcSbkIk2B-dFXkm0T_9oG1hNzmUrs_PLz9dOVL2JCn6sckHk84SGzophhMlLoP-yOWLK-te-qcU1g?purpose=inline)

[fptshop.com.vn](https://fptshop.com.vn/tin-tuc/danh-gia/git-la-gi-169819?utm_source=chatgpt.com)

- Every developer has a complete copy of the project repository.
- Developers can work independently without an internet connection.
- Changes can be shared with other developers.
- It is more reliable because every developer has a copy of the repository.

Examples:

- Git
- Mercurial

## Difference Between the Three Types

| Feature       | Local VCS      | Centralized VCS  | Distributed VCS            |
| ------------- | -------------- | ---------------- | -------------------------- |
| Storage       | Local computer | Central server   | Every developer's computer |
| Internet      | Not required   | Usually required | Not always required        |
| Collaboration | Limited        | Supported        | Highly supported           |
| Backup        | Local          | Central server   | Multiple copies            |
| Example       | RCS            | SVN, CVS         | Git, Mercurial             |

## What is Git?

[SaaS Web Design Agency | Ramotion](https://images.openai.com/static-rsc-4/b9KWi3rbx7VUKaMm57fI9Oc83cngNGmOTSnN6lkQ5OUpAbztl7ppFDmKLVDqn0Tzfj8caqpEJNJQ4pry3t3InXP0qMdub9sKnGXknA_V9F_6NfEoS3kqNEnu60xa8yIFex3nFnmlYXj1EyuHVGlyEJcaFx1z7YyT_ietl2y59a8?purpose=inline)

Git

Git is a popular distributed version control system used by developers to track changes in source code and collaborate on projects.

Some important Git commands:

| Command      | Purpose                              |
| ------------ | ------------------------------------ |
| `git init`   | Creates a new repository             |
| `git add`    | Adds files to staging                |
| `git commit` | Saves changes                        |
| `git push`   | Uploads changes to remote repository |
| `git pull`   | Downloads and integrates changes     |
| `git clone`  | Copies a repository                  |

In simple words: A Version Control System helps developers save, track, manage, and share different versions of their projects.

Important for exams/interviews: Remember the three types: Local VCS, Centralized VCS, and Distributed VCS. Git is a Distributed Version Control System.
