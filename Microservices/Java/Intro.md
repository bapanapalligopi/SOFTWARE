What are the microservices requirements?


Let's build  the employee customer management

The following components will need Employee, customers, courses, and address
and all having the crud api's

Monolithic - all our components placed in same package file

<img width="932" height="412" alt="image" src="https://github.com/user-attachments/assets/0341d2f1-abbb-43cd-80ae-d9d00a4a410b" />
<img width="892" height="527" alt="image" src="https://github.com/user-attachments/assets/f7a3c1be-00eb-4634-95e1-3a607434db2e" />

problems, challenges in monolithic

Implement some new features / fix some bugs 

<img width="949" height="591" alt="image" src="https://github.com/user-attachments/assets/1162225c-feee-40e4-a2ec-af71f1a5fc5e" />
If changes fail, then other components will be affected because the entire application will encounter deployment problems

<img width="949" height="544" alt="image" src="https://github.com/user-attachments/assets/09354aab-162c-46a1-ac9b-db5690e064ee" />

challenge -2
For new users/ customers -- Load

<img width="961" height="572" alt="image" src="https://github.com/user-attachments/assets/cf25f400-84f0-4389-9a00-d34e58d069cc" />
solution

same code on 3 different servers

<img width="950" height="432" alt="image" src="https://github.com/user-attachments/assets/afc7f276-394c-4b08-af72-183a9e3d0b05" />

<img width="955" height="616" alt="image" src="https://github.com/user-attachments/assets/e0ecd92e-bf26-4536-85bd-93297fb6b00a" />
problem - traffic for only the customer but also deploys other modules in 3, becuase of customer module is not deployed dependently, it leades cost manamegement 

<img width="978" height="538" alt="image" src="https://github.com/user-attachments/assets/a311de43-dc4a-4f7b-a360-a1c69ab27db7" />

intro to microservices

<img width="962" height="608" alt="image" src="https://github.com/user-attachments/assets/10692638-7d4e-4e84-852c-2c140cc9a1a0" />

All are separate modules- 4 different springboot applications

<img width="838" height="220" alt="image" src="https://github.com/user-attachments/assets/e8caf0ff-ec2b-40f5-92b6-1ec23b65d403" />

it is doing some service to the busineess need 

<img width="845" height="527" alt="image" src="https://github.com/user-attachments/assets/d202fe1a-8eec-48fa-b1fc-a321bf49323c" />
<img width="589" height="594" alt="image" src="https://github.com/user-attachments/assets/f999b9a0-ff03-4b72-99a9-64a46aac6a07" />
<img width="905" height="271" alt="image" src="https://github.com/user-attachments/assets/2b481d7d-d2b1-4cb4-b96d-9ef3e556168e" />

<img width="929" height="563" alt="image" src="https://github.com/user-attachments/assets/5f41d625-bc6f-475d-a360-d58c822b38ac" />

<img width="931" height="549" alt="image" src="https://github.com/user-attachments/assets/f4116c9d-a1a8-441e-b775-2be9774245fa" />
 <img width="960" height="578" alt="image" src="https://github.com/user-attachments/assets/4df4d3a3-ff53-4c1b-89ab-161998da510a" />



Communication

<img width="947" height="604" alt="image" src="https://github.com/user-attachments/assets/e77b7157-5d2b-45b4-ad24-aeb986581053" />

<img width="959" height="584" alt="image" src="https://github.com/user-attachments/assets/70e93bcb-eea1-4662-b95a-dcb07127c1df" />

Independently  Deployable
Each Application can be tested differently
Code changes on one app don't need an entire application testing
dev working on one service, shouldn't  require the entire application knowledge

<img width="856" height="189" alt="image" src="https://github.com/user-attachments/assets/8d7a325b-6c38-41b6-a5f6-380701a4bb92" />

<img width="939" height="589" alt="image" src="https://github.com/user-attachments/assets/7ca6fc0c-2c7e-4a4e-b4b0-6152030ab9e4" />

<img width="943" height="435" alt="image" src="https://github.com/user-attachments/assets/696a9e7f-07e1-4253-8971-bc43feebcf62" />


 
