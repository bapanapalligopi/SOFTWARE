## What is SVN?

SVN (Subversion) is a Centralized Version Control System (CVCS) used to manage and track changes made to files and source code in a software project.

It allows multiple developers to work on the same project using a central server.

In simple words, SVN stores project files in one central location and keeps track of every change made by developers.

## How SVN Works

[Architecture and Design of Subversion - SVN (Part 1)](https://images.openai.com/static-rsc-4/WpPRkoBnsgpAhuOTL_hTGzgiyzG1GFExV3BDFCyBCBKo1rWabg5nuBbya08s3UvIqHkeS_i7EtptH3YuLWgjRi0JMlCU04HfOpkDyv01VF_36NheACr2vGq9eKElhTIgwI3Zusu5M3Ewto7bZXjQo68i6t8eLeOB6rvXIoxX2YU?purpose=inline)

[codentrick.com](https://codentrick.com/architecture-and-design-of-subversion-svn-part-1/?utm_source=chatgpt.com)

1. Central Repository: All project files are stored on a central server.
2. Checkout: Developers download a working copy of the project.
3. Modify: Developers make changes to files.
4. Commit: Developers upload their changes to the central repository.
5. Update: Developers download the latest changes made by other team members.

## Important SVN Commands

| Command        | Purpose                                 |
| -------------- | --------------------------------------- |
| `svn checkout` | Downloads a working copy                |
| `svn update`   | Gets the latest changes                 |
| `svn add`      | Adds new files                          |
| `svn commit`   | Saves changes to the central repository |
| `svn status`   | Shows modified files                    |
| `svn log`      | Displays change history                 |
| `svn delete`   | Deletes files from version control      |
| `svn revert`   | Discards local changes                  |

## Advantages of SVN

- Easy to manage projects centrally.
- Supports multiple developers.
- Maintains version history.
- Allows developers to restore previous versions.
- Provides access control and permissions.

## Disadvantages of SVN

- Depends on a central server.
- Offline work is limited.
- Central server failure can affect the entire team.
- Branching and merging can be more complicated than in Git.

## Difference Between SVN and Git

[Apache Subversion (SVN) | Julio Batista Silva](https://images.openai.com/static-rsc-4/FhaDY0n4naSedvBLDl8RqLnbax0QbcMvZloqkPgy6utS2ODEwHephfexKXC7nu1wtd09-j8qhC0TPz91BfONuZrgx9Lftw6SRMHc87kWxPwPAjUBDzJGkpyyZLTGibYCzgji1XHdP4S-Xq24xe5LUAyg8qPzzt419cLWEoE8yDI?purpose=inline)

SVN

Centralized VCS

[File:Git-logo-orange.svg - Wikimedia Commons](https://images.openai.com/static-rsc-4/cqLM-XX3mHgtdYY3lkjylPDBnXMbRVdv7W2Sd3odgxcvZVrsfxUmVUBRzhzVPbGGnNFmShHQlTzOgmwXdjuzc0YHF8256ZQanVJ6gDg8xkRN9UH8Yu08B0MOpkXgMgd3Ju8Q9cOBq_dvXpD_yxjEv8ZHYJ3OPCPUJ1Fj-BxEGKc?purpose=inline)

Git

Distributed VCS

| SVN                       | Git                                         |
| ------------------------- | ------------------------------------------- |
| Centralized system        | Distributed system                          |
| Uses a central repository | Every developer has a local repository      |
| Offline work is limited   | Supports offline work                       |
| Uses `svn commit`         | Uses `git commit`                           |
| Example: SVN server       | Example: GitHub, GitLab (hosting platforms) |

## Real-Time Example

Suppose three developers are working on a banking application:

- Developer 1 works on the Login page.
- Developer 2 works on the Registration page.
- Developer 3 works on the Payment page.

All three developers download the project from the SVN central repository, make their changes, and commit them back to the server.

SVN maintains the history of all these changes.

Remember for interviews

SVN stands for Apache Subversion. It is a Centralized Version Control System (CVCS) that helps developers track, manage, and maintain different versions of project files.

I can also explain the SVN workflow step by step with a practical example of checkout, update, add, and commit commands.
