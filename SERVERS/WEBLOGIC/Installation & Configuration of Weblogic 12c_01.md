# **How to Install and Configure Oracle WebLogic Server 12c**

Let's learn WebLogic Server 12c installation and configuration step by step, just like you would do it in a real-time project.

We will cover the complete process, starting from installing Java and WebLogic, creating a domain, configuring servers, and accessing the WebLogic Administration Console.

[Getting Started Administering Capture](https://images.openai.com/static-rsc-4/2UkVMZH3w7LmGu5nbfAFauCJ-k8xbmD2kyN4cWD97i2f-ZfDICcCveTuyml6VKRZyOl2PqnOImtJ0rb6m8aAIqnO1HOroHrScc9eqXh8LadUCPs42Us3dM6gmOlCAblvDsRDEbU3BGyrcTBy8tLfXGWEwG3fkmGWQ-bxIWH22lk?purpose=inline)

[docs.oracle.com](https://docs.oracle.com/middleware/12213/wcc/admin-capture/GUID-35B013BF-9F63-4D3E-9E75-1CD8B0D21207.htm?utm_source=chatgpt.com)

## **1. Understand the installation architecture**

Before installing WebLogic, understand what components we need.

**Operating System**

Windows / Linux

**JDK (Java Development Kit)**

Java runtime required by WebLogic

**WebLogic Server 12c**

Application server software

**WebLogic Domain**

Administration Server + Managed Servers

## **2. Prerequisites**

For a basic learning environment, prepare:

| Component        | Example                                               |
| ---------------- | ----------------------------------------------------- |
| Operating System | Windows 10/11 or Linux                                |
| WebLogic         | 12c (12.2.1.x)                                        |
| Java             | JDK version certified for your exact WebLogic release |
| RAM              | 8 GB recommended for a comfortable lab                |
| Disk Space       | 15–20 GB free                                         |
| Browser          | Chrome or Firefox                                     |

**Important:** WebLogic 12c has multiple releases, including 12.1.3 and 12.2.1.x. Their supported JDK versions differ. Don't install an arbitrary latest JDK.

## **3. Download WebLogic Server 12c**

For this tutorial, let's use **WebLogic Server 12.2.1.4**, a commonly used 12c release.

Download from Oracle:

- [Oracle WebLogic Server 12c Downloads](https://www.oracle.com/middleware/technologies/weblogic-server-downloads.html?utm_source=chatgpt.com)
- [Official WebLogic 12.2.1.4 Installation Guide](https://docs.oracle.com/en/middleware/fusion-middleware/12.2.1.4/wlsig/installing-and-configuring-oracle-weblogic-server-and-coherence.pdf?utm_source=chatgpt.com)

Choose the **Generic Installer** for a full installation.

The installer file is typically named:

```
fmw_12.2.1.4.0_wls_lite_generic.jar
```

You may need to extract the downloaded ZIP archive first.

## **4. Install Java JDK**

For WebLogic 12.2.1.4, use a certified 64-bit JDK 8 installation. Oracle's documentation specifies JDK 8 update 211 or later for this release, subject to the supported-system certification.

Example installation directory:

```
C:\Java\jdk1.8.0_211
```

Set environment variables in Windows:

1. Open System Properties.
2. Select Advanced.
3. Click Environment Variables.
4. Create the following variables.

| Variable  | Value                |
| --------- | -------------------- |
| JAVA_HOME | C:\Java\jdk1.8.0_211 |
| PATH      | Add %JAVA_HOME%\bin  |

Open Command Prompt and verify:

```
java -version
```

Expected output will show Java 1.8.

Also check:

```
echo %JAVA_HOME%
```

You should see your JDK installation path.

## **5. Install WebLogic Server**

Now we install the actual WebLogic software.

**Step 1:** Open Command Prompt.

**Step 2:** Navigate to the directory containing the downloaded installer.

For example:

```
cd C:\Oracle\Software
```

**Step 3:** Execute the installer using Java:

```
java -jar fmw_12.2.1.4.0_wls_lite_generic.jar
```

[Installing WebLogic Server](https://images.openai.com/static-rsc-4/ojrJURZ31mvlLIoxBO1uY6h0Ko2GeV__LkdQG09MkZrSj_J3VhiFVexijK9-XnqxL67BGlHvu2NuJR6lsC5jsbBkin3zlneU0z8G4B8aNytrGfOHcXrta3t2uTmCCbLkWAPbqwEod59DY8yFBTIasZK8HkCK1ZhSgtxMMbfM0B4?purpose=inline)

[docs.oracle.com](https://docs.oracle.com/cd/E49933_01/ias.320/ias_install/src/tiim_wls_install_server.html?utm_source=chatgpt.com)

**Step 4:** Follow the installation wizard.

You will see screens similar to these:

| Screen                | What to do               |
| --------------------- | ------------------------ |
| Welcome               | Click Next               |
| Auto Updates          | Skip if not required     |
| Installation Location | Select Middleware Home   |
| Installation Type     | Select WebLogic Server   |
| Prerequisite Checks   | Verify checks pass       |
| Security Updates      | Configure as appropriate |
| Installation Summary  | Review settings          |
| Installation Progress | Wait for completion      |

Use this example installation location:

```
C:\Oracle\Middleware\Oracle_Home
```

After installation, your directory structure will look approximately like this:

```
C:\Oracle\Middleware\Oracle_Home
    |
    |-- oracle_common
    |
    |-- wlserver
    |
    |-- OPatch
    |
    |-- oui
```

**Important:** Installing WebLogic software does not automatically mean that you have created a WebLogic domain. Domain creation is the next step.

## **6. Create a WebLogic Domain**

Very important practical step

First, understand what a domain is.

A **WebLogic Domain** is a logical administrative boundary containing WebLogic server instances, configurations, and resources.

We will create a domain named:

```
mydomain
```

**Step 1:** Open the Configuration Wizard.

Navigate to:

```
C:\Oracle\Middleware\Oracle_Home\oracle_common\common\bin
```

Run:

```
config.cmd
```

[Oracle WebLogic Server 12c (12.2.1): Creating a Domain](https://images.openai.com/static-rsc-4/-OUEZrOjnfQQJTVxM9Gnm55R86pqTYG2subvlKRFJmhIJZ6huc9_rQrCuZy09aXHVsl53tbv2nNlbNaMmM0LG46AE1PB0odaijjFNa9uM3S7w8dO9gkSl0fIMnAVowEB01e0u3jB6qQZq_l7hiUD0tel58PASz772BK2j0VMTyA?purpose=inline)

[oracle.com](https://www.oracle.com/webfolder/technetwork/tutorials/obe/fmw/wls/12c/12_2_1/01-04-004-CreateDomain/creatingadomain.html?utm_source=chatgpt.com)

**Step 2: Select Domain Type**

Choose:

```
Create a new domain
```

**Step 3: Select Domain Location**

Enter:

```
C:\Oracle\Middleware\Oracle_Home\user_projects\domains\mydomain
```

**Step 4: Select Domain Template**

Choose:

```
Basic WebLogic Server Domain
```

Click Next.

**Step 5: Configure Administrator Account**

Enter:

```
Username: weblogic
Password: YourStrongPassword
```

Remember this username and password. You will use them to log in to the Administration Console.

**Step 6: Select Domain Mode**

For learning purposes, select:

```
Development
```

Select the JDK you installed earlier.

**Step 7: Advanced Configuration**

For a basic installation, you can skip advanced configuration.

**Step 8: Create Domain**

Click Create and wait until the domain creation process completes.

[Domain Creation and Cluster Configuration](https://images.openai.com/static-rsc-4/H1YJOLSRf6OKdlTgURt-TscRBQTbIMGRchgw8vtT6PK0lwGr79iuubhQVbJ-9xVUv94v-ypUte3yrPtvVXhk99rZVKK1WkVIaAh2r_jFKzh2xB5UadJfg_pNNDsl4UdJWxtcuGIEKaKQxUx79eheM-wXxbNW1eNHO59u7ARoAsI?purpose=inline)

[docs.oracle.com](https://docs.oracle.com/en/industries/financial-services/microservices-common/14.7.2.0.0/cadig/domain-creation-and-cluster-configuration.html?utm_source=chatgpt.com)

Your domain has now been created.

## **7. Start WebLogic Administration Server**

Now we need to start the WebLogic server.

Navigate to your domain's `bin` directory:

```
cd C:\Oracle\Middleware\Oracle_Home\user_projects\domains\mydomain\bin
```

Execute:

```
startWebLogic.cmd
```

The server will start and initialize its services.

[使用 Idea 远程断点调试 Weblogic 服务器的操作步骤 - Defonds - 博客园](https://images.openai.com/static-rsc-4/Rzo8ztmnrHm9pd4L0A_kBqnr6iJEQzG9ypJTyq1peBGqIVVVHtp2elo7dAE5kN-9Bh6hQP-q44pXTW091gD9pHgzk9WcquqL_CGiJpiZD6Zae_BfI9fatOhI-CzEBNkzC-EO8hAHTpNG_CA6Ie-219oydM6pSg900lL5SAqrlKg?purpose=inline)

[cnblogs.com](https://www.cnblogs.com/defonds/p/15332020.html?utm_source=chatgpt.com)

Look for a message similar to:

```
<Server state changed to RUNNING>
```

RUNNING

This means your Administration Server has started successfully.

## **8. Access WebLogic Administration Console**

Open your browser.

Enter this URL:

**WebLogic Administration Console**

Local access

## [**http://localhost:7001/console**](http://localhost:7001/console?utm_source=chatgpt.com)

Open Administration Console&#x20;

Login using:

```
Username: weblogic
Password: YourStrongPassword
```

[Oracle WebLogic Server 12c (12.2.1): Deploying the MedRec Sample       Application](https://images.openai.com/static-rsc-4/TEgh3Uxl2-sYYvpqicD5cV-3RWOguyEkLwui9byF4jnpYBLAle8W6iaUjAe43DQgjiFewUOX_bT6Zu_KnjxRv7guWMhh6KFFeYd3GBVn7-w5focA4lcowQiNKTuhTHU_NR1N4DSr_Q8TrdVrrg96m8ur8XLRogQNj1PudxJO51s?purpose=inline)

[oracle.com](https://www.oracle.com/webfolder/technetwork/tutorials/obe/fmw/wls/12c/12_2_1/02-34-004-DeploySampleApplication/deploysampleapplication.html?utm_source=chatgpt.com)

After login, you should see the WebLogic Administration Console.

From here, you can:

- Create and manage servers.
- Deploy Java applications.
- Configure JDBC data sources.
- Monitor server performance.
- Manage security settings.
- Configure clusters.

## **9. Understand Administration Server and Managed Server**

This is one of the most important concepts in WebLogic administration.

[Introduction](https://images.openai.com/static-rsc-4/s-eJdw7yTDpcdY5prgWN718B-oSaa1i33yyiV1ynfRjBBH-xXpsztrtNgpToMkGCp4yPISyEDKwtxz9c_Wr4h-wIX1Gn72eWMW474QWmv-0WSJljCejemfQCGHUmLtPZVYC64qpTEo3ENna4XOBBmIR-0UkiCTpjKm7XOnHlRqo?purpose=inline)

[docs.oracle.com](https://docs.oracle.com/en/middleware/fusion-middleware/12.2.1.4/wldcw/introduction.html?utm_source=chatgpt.com)

**Administration Server**

- Central management server of a domain.
- Provides the Administration Console.
- Used to configure and manage Managed Servers.

**Managed Server**

- Runs deployed Java applications.
- Handles application requests.
- Can be configured independently from the Administration Server.

For example:

| Server         | Port | Purpose               |
| -------------- | ---- | --------------------- |
| AdminServer    | 7001 | Domain administration |
| ManagedServer1 | 7003 | Runs applications     |
| ManagedServer2 | 7005 | Runs applications     |

These Managed Servers are examples; they are not automatically created during basic domain creation.

## **10. Create a Managed Server**

Let's create one Managed Server.

1. Login to WebLogic Console.
2. Navigate to **Environment → Servers**.
3. Click **New**.
4. Enter the following details:

```
Name: ManagedServer1
Listen Address: localhost
Listen Port: 7003
```

5. Click Next.
6. Review the configuration.
7. Click Finish.

Your new Managed Server should appear in the Servers list.

For a simple single-machine lab, you can keep it in the same domain as the Administration Server.

## **11. Start the Managed Server**

Open another Command Prompt.

Navigate to:

```
C:\Oracle\Middleware\Oracle_Home\user_projects\domains\mydomain\bin
```

Execute:

```
startManagedWebLogic.cmd ManagedServer1 http://localhost:7001
```

Enter the credentials if prompted.

Wait until the Managed Server reaches the RUNNING state.

## **12. Verify the Complete Installation**

Your basic WebLogic environment should now look like this:

## **My WebLogic Domain**

**AdminServer**

RUNNING

Port: 7001

**ManagedServer1**

RUNNING

Port: 7003

**ManagedServer2**

Optional

Port: 7005

Verify these things:

- WebLogic software installed.
- Domain created.
- Administration Server started.
- Administration Console accessible.
- Managed Server created.
- Managed Server started.

## **13. Important WebLogic commands**

Keep these commands handy.

| Operation                   | Windows command                                                 |
| --------------------------- | --------------------------------------------------------------- |
| Start Admin Server          | `startWebLogic.cmd`                                             |
| Stop Admin Server           | `stopWebLogic.cmd`                                              |
| Start Managed Server        | `startManagedWebLogic.cmd ManagedServer1 http://localhost:7001` |
| Open Configuration Wizard   | `config.cmd`                                                    |
| Open Administration Console | `http://localhost:7001/console`                                 |

## **14. Common installation problems**

| Problem                  | Possible solution                             |
| ------------------------ | --------------------------------------------- |
| Java not recognized      | Configure JAVA_HOME and PATH                  |
| Installer not opening    | Check JDK version and installer compatibility |
| Port 7001 already in use | Check for another process using port 7001     |
| Server failed to start   | Check server logs                             |
| Console not opening      | Verify AdminServer is RUNNING                 |
| Authentication failed    | Verify administrator credentials              |

Check the AdminServer logs here:

```
mydomain/servers/AdminServer/logs/AdminServer.log
```

## **15. Official Oracle learning resources**

These are useful references for hands-on practice:

1. [Oracle WebLogic Installation Guide](https://docs.oracle.com/en/middleware/fusion-middleware/12.2.1.4/wlsig/installing-oracle-weblogic-server-and-coherence-software.html?source=:so:fb:or:awr:ocl:::cloud\&utm_source=chatgpt.com)
2. [Planning WebLogic Installation](https://docs.oracle.com/en/middleware/fusion-middleware/12.2.1.4/wlsig/planning-oracle-weblogic-server-installation.html?utm_source=chatgpt.com)
3. [WebLogic Software Downloads](https://www.oracle.com/middleware/technologies/weblogic-server-downloads.html?utm_source=chatgpt.com)
4. [System Requirements and JDK Compatibility](https://docs.oracle.com/en/middleware/fusion-middleware/12.2.1.4/sysrs/system-requirements-and-specifications.html?utm_source=chatgpt.com)

**Note:** WebLogic 12.2.1.4 is an older release. For production, check Oracle's current support and security patch requirements.

## **Let's make this a practical installation**

I can guide you through each step, including commands, screenshots to look for, and troubleshooting.

**First, which operating system are you using?**

**1. Your operating system**

Windows 11

Windows 10

Linux (Oracle Linux / RHEL)

Ubuntu Linux

**2. Which WebLogic version?**

12.2.1.4

12.2.1.3

12.1.3

**3. Is Java already installed?**

No

Yes – JDK 8

Yes – another version

Start my installation guide
<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/1664b49b-aa1a-4b6c-9240-65083f575464" />
https://www.oracle.com/middleware/technologies/weblogic-server-downloads.html?utm_source=chatgpt.com
<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/949de598-7093-4475-af22-727cf21caec4" />
install java8
<img width="401" height="314" alt="image" src="https://github.com/user-attachments/assets/220bce37-25b9-418e-9ad9-c56fe795e851" />
<img width="398" height="304" alt="image" src="https://github.com/user-attachments/assets/70b1319a-2132-4850-a04a-32aa1505eb4f" />
<img width="550" height="287" alt="image" src="https://github.com/user-attachments/assets/65d0ff45-f8f6-414a-aaae-b7328cd772ce" />
<img width="541" height="167" alt="image" src="https://github.com/user-attachments/assets/a79661eb-cd5d-4c2c-a30d-3ca0b4cf9e69" />
Install WebLogic Server
goto <img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/f233a361-2aa0-478e-9dfa-1fdb9bd92320" />
<img width="626" height="190" alt="image" src="https://github.com/user-attachments/assets/6467013d-b909-45f1-87d4-b2433ea02b4c" />
Launcher log file is C:\Users\chila\AppData\Local\Temp\OraInstall2026-11-15_12-39-25PM\launcher2026-11-15_12-39-25PM.log.
Extracting the installer . . . . . . . . Done
The OpenJDK JVM is not supported on this platform.
The log is located here: C:\Users\chila\AppData\Local\Temp\OraInstall2026-11-15_12-39-25PM\launcher2026-11-15_12-39-25PM.log.
<img width="640" height="227" alt="image" src="https://github.com/user-attachments/assets/88b6bb2f-4781-4c28-bf01-663e29a73e0c" />
<img width="511" height="341" alt="image" src="https://github.com/user-attachments/assets/585434c3-82a2-45c9-ba1e-9e4224a5baf0" />
<img width="419" height="325" alt="image" src="https://github.com/user-attachments/assets/627dc7aa-c7c8-42d9-9bf8-9b1607418656" />
<img width="402" height="308" alt="image" src="https://github.com/user-attachments/assets/a6c48e52-8043-4d0f-b631-05549b498466" />
<img width="410" height="300" alt="image" src="https://github.com/user-attachments/assets/1ade83ca-4087-451b-b2a6-25bc38d481cf" />
<img width="403" height="299" alt="image" src="https://github.com/user-attachments/assets/e89272b6-9d1e-4c0d-86f0-f504d0281501" />
<img width="398" height="294" alt="image" src="https://github.com/user-attachments/assets/7dd6b248-554e-4b53-9622-9e7ef6463590" />
<img width="951" height="472" alt="image" src="https://github.com/user-attachments/assets/2b5e1c3d-d23a-4eb6-aef2-91593bb77de0" />
http://localhost:7001/console/login/LoginForm.jsp -> login
gopi,Gopi1239@2026#17
<img width="287" height="185" alt="image" src="https://github.com/user-attachments/assets/5c41dc67-8784-4bdd-9973-4b745818f6ce" />

<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/65ac9db5-7d49-4114-95a7-44ad2780fe95" />
<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/fa855827-8288-470e-b43c-0f9f889084c7" />
creating managing servers
<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/759c77fc-0868-40cc-a1e8-f6dd35454c35" />
<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/84ed0b30-aa58-41cd-ba30-feb80932798e" />
<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/73bf9d95-fcd8-473f-9cd9-945486b016a9" />
run managed server
C:\Oracle\Middleware\Oracle_Home\user_projects\domains\base_domain\bin
<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/897d1d67-f6a6-4776-b141-fa2cb7a84821" />
<img width="956" height="295" alt="image" src="https://github.com/user-attachments/assets/ba5c0d6d-a8ef-4211-b5b0-d906d0581844" />





