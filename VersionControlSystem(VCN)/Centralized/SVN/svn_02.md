# How to Set Up SVN in Windows

You can set up SVN (Apache Subversion) on Windows using TortoiseSVN. It provides a graphical interface to manage SVN repositories without typing commands.

I'll explain the setup step by step, including how to create a repository, checkout files, and commit changes.

## Step 1: Download SVN for Windows

You need two things:

1. TortoiseSVN – A graphical SVN client.
2. SVN command-line tools – To execute SVN commands using Command Prompt.

[Open Source For Geeks: TortoiseSVN icons not showing up under Windows 7](https://images.openai.com/static-rsc-4/qAdO8wxRZ3ttWAgjWj4nww6z3qTFKucB1rrqH6AAI-3rL17T8KSWqrxc8tlJEAoySL_EDlQTrJsnRNZlhfwkUtrqyLp0VPmPQC_32nMg7FCIt7YN5r50KTF3ewqXi_Qua5H3lMRmXucPdIo5ccrLSj7arTKFt_pC1DBESqsyaf4?purpose=inline)

TortoiseSVN

Graphical interface for SVN operations.

[Download TortoiseSVN](https://tortoisesvn.net/downloads.html?utm_source=chatgpt.com)

[Icône de Apache subversion logo](https://images.openai.com/static-rsc-4/V8PimXRFvMzVhsTwQXCa5Bov9rLxeZIz04ph5EAZZQjp8OAnX8UuROcnRaJIg3aKmpmSbsJSjzL3kwDWFYqyIcqrEofeKy-A--LfK9MvPZGHpA5Nt76Sq5WizcyKzSVz_NmSnWDhgzUuj7Luxu2zYSEtaT675HvRNgc_qly0e9s?purpose=inline)

Apache Subversion

SVN command-line tools and repository software.

[Download SVN packages](https://subversion.apache.org/packages.html?utm_source=chatgpt.com)

## Step 2: Install TortoiseSVN

[TortoiseSVN安装、使用教程 - 疯狂的机器人 - 博客园](https://images.openai.com/static-rsc-4/Sa6mDOwpF4NJ2-1u4zzLbylyi0zs_SFfkqoVLKG3nsNy1-R6azwOVg1kxVxG0dCQr3w_wQjoHiOQ0JTXRqJcVhp6OjVqhyVJpGQyy4ShADAqaA9Avw_l1qt1ITmzQ1ZPyU9WLXsMVEr2oj-qm45KHFPSjvDYYR7rkarF6oWqf6Q?purpose=inline)

[command line - Where is svn.exe in my machine? - Stack Overflow](https://images.openai.com/static-rsc-4/5LVWRpS6TCNeOs2VK9CIkOw2d80ZJpy_ymDSUDwLvDH9aAgx-jvs8K_hOTt7HTDstdYOY1C2ahnOiDg7Dp6dSuO-H-oshAA0NhwuNJs2z6TknP46_NxuMm_UKP-IGmSlfHqa85TH35vHpUF8bMTnIr7FcdSkuj6Q6DdYX9nl_Mk?purpose=inline)

[TortoiseSVN 下载与安装、汉化-阿里云开发者社区](https://images.openai.com/static-rsc-4/bLsN4qKUofOJiMElj85dwDrUPWDhanQD4VClY-S_HvWyfvZmXsbyJyip2vr_yjwFuCy8PJ5gs-Oh6akL4sn1B9y7QLddT9pdA3AeWftwEOb0ZSR3KN5RcWAznJuTP5V5Vph1xKq52-ptZhZGJNrDLCKByf42DCdb8TdCRoa-jx0?purpose=inline)

5

1. Download the Windows installer.
2. Double-click the downloaded `.msi` file.
3. Click Next.
4. Accept the license agreement.
5. Select the default installation options.
6. Click Install.
7. Restart Windows if required.

After installation, right-click anywhere on your desktop.

You should see SVN-related options such as:

- SVN Checkout
- TortoiseSVN

## Step 3: Install SVN Command-Line Tools

If you want to use SVN commands in Command Prompt:

1. Run the TortoiseSVN installer again if necessary.
2. Select the command-line client tools option if available.
3. Complete the installation.
4. Open Command Prompt.

Run:

```
svn --version
```

If installation is successful, you will see the SVN version.

Note: TortoiseSVN works without separate command-line tools if you only need its graphical interface.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://tortoisesvn.net\&sz=32)

TortoiseSVN+1



## Step 4: Install SVN Server (For Team Projects)

If you want to create your own central SVN server on Windows, install VisualSVN Server.

[SVN Basics - Module 1: Core Components and Installing Visual SVN Server](https://images.openai.com/static-rsc-4/kRrnnAtkilq4MysHS1OgbfMQ4BH1XzFK9iObcq6wxeeM30ILd8obZABKSrIa5PG9zt-3jBDGRhbTMypDJSgbjZbPkgdUCq49su_DtL25V4-czMZjO5N9PatWBvEIOAq82yfWP8nF6SNy29JeIAmGxzrNKCCiW7sk4VTZuoq758A?purpose=inline)

VisualSVN Server

Creates and manages SVN repositories on Windows.

[Download VisualSVN Server](https://www.visualsvn.com/server/download/?utm_source=chatgpt.com)

Installation steps:

1. Download VisualSVN Server.
2. Run the `.msi` installer.
3. Select VisualSVN Server and Administration Tools.
4. Keep HTTPS enabled.
5. Complete the installation.
6. Open VisualSVN Server Manager.

[image](https://www.google.com/s2/favicons?domain=https://www.visualsvn.com\&sz=32)

VisualSVN Server

## Step 5: Create an SVN Repository

[Install and manage Visual SVN Server | o7planning.org](https://images.openai.com/static-rsc-4/dy9xdt4Cj9irYHnhVqui6UNs35K8uOE4AH2rK32gs-ROpAUsGDgDneiToohSMmRdfCpHcJV7yf7Yk_TEFIB6JqQyVVKpd9y9U1CVTcQXcP74aHrXQHaZTU3zMWbYiUg3_1ZSetLzaZ6hsCxJH12AdRftU7J5PDj5LvtuvOhuTvE?purpose=inline)

[o7planning.org](https://o7planning.org/10207/install-and-manage-visual-svn-server?utm_source=chatgpt.com)

1. Open VisualSVN Server Manager.
2. Right-click Repositories.
3. Select Create New Repository.
4. Enter the repository name, for example:

```
MyFirstProject
```

5. Select the default repository structure (trunk, branches, tags).
6. Create the repository.
7. Configure user permissions.

Your repository is now ready.

## Step 6: Checkout the Repository

Now open your desktop.

1. Create a folder called `SVNProjects`.
2. Right-click inside that folder.
3. Select SVN Checkout.
4. Enter your repository URL.

Example:

```
https://localhost/svn/MyFirstProject
```

5. Select the checkout directory.
6. Click OK.
7. Enter your SVN username and password if prompted.

Your project will be downloaded to your computer.

## Step 7: Perform Your First Commit

Let's create a file and upload it to SVN.

1. Open your checked-out project folder.
2. Create a file called `test.txt`.
3. Write:

```
Hello SVN!
This is my first SVN project.
```

4. Right-click the file.
5. Select TortoiseSVN → Add.
6. Right-click the project folder.
7. Select SVN Commit.
8. Enter a message:

```
First commit
```

9\. Click OK.



Success

&#x20;Your first file is now stored in the SVN repository.



## SVN Setup Summary

1. Install TortoiseSVN

   SVN client on your Windows computer
2. Install VisualSVN Server

   Central SVN server
3. Create Repository

   MyFirstProject
4. Checkout Repository

   Download project to your computer
5. Add and Commit Files

   Upload your changes to SVN

## One question: Which setup do you need?

Personal practice – SVN on my own Windows laptop

Team project – SVN server with multiple developers

Command line – SVN commands using CMD

Continue
<img width="612" height="376" alt="image" src="https://github.com/user-attachments/assets/2001c173-3d26-405b-be12-6da68ae1d461" />
<img width="612" height="376" alt="image" src="https://github.com/user-attachments/assets/7849c7a6-86dd-4249-8de9-7649ce26d964" />
<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/4249a63d-dcc1-4892-834d-24d29213c989" />
