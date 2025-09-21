what is the need for data engineers in todays world??  
why do we need these professionals..  

if data is used efficiently ..we can achieve operational efficiency ..  
this improves customer experience..which in turn boosts customer satisfaction ..  
this increase trust in the brand ..  which in turn leads to increased sales and profits..  

Walmart uses big data to predict the demand for stocks and stock it up in appropriate stores before hand  
and hence when a customer walks in to the store ..he find the product and buys it ..  
satisfied ..  
and increased sales and profits  ..

so like these there are n number of use cases for data  ..

but if this data is not always in a really good consumable format   
it will be in all soughts of places  
it needs to be orchestrated and brought to a central place  
this data will be huge so we need to go for big data processing  spark batch and streaming  
to store transformed data we need something called data warehouse  
to transform this data there will be tools ..

so end to end need to be aware of ..how to get this data..  
how to appropriately store it ..  
and how to tranform it in a way that could be consumed by thr down stream teams for machine learning and analytics purposes..  this is the customer need ..
you need to prepare in such a way to efficiently solve this customer need..  

to orchestrate and stuff ..python is need ..
to transform this data ..both python and sql are really useful ..
data tranformer,data orchestrator,data warehouse ,distributed batch and stream processing are these can be found in any one cloud so 1 cloud knowledge is important  
this is primary ..if you can achieve this..then really good 




git history
we can use git head~2  git head^2  git head {1 month ago }  to know the parents of present commits  
git head {1 month ago} tells me where the head was 1 month commit ..to which commit it was pointing to.  

git blame file_name  
this can give us the changes that happened in that particular file  

git diff head head^2  
this can give the difference between these 2 commits  

git log   
this can give us a whole host of information about history  

<img width="337" height="238" alt="image" src="https://github.com/user-attachments/assets/a6296894-9ba1-45b8-9dc0-b57b3348bf6b" />


<img width="530" height="144" alt="image" src="https://github.com/user-attachments/assets/1f5c75e5-5d0b-4656-90b8-44a0b599ce87" />

**git commit --amend**  
what this does is ..if we had commited earlier with some changes..and we have a new change ..  
but we dont really want to have a fresh commit for this ..then we can amend this change to the earlier commit  
and the head pointer moves to the adjacently created new version of this commit  
and the older commit will go away with garbage collector  

git rebase -i origin/master
interactive history rebase

git reflog  
this will give the logs for all the commit,rebase etc that we have performed in the system  

cases when meddling with history becomes necessary  
<img width="670" height="300" alt="image" src="https://github.com/user-attachments/assets/8757687d-6afb-4c18-92ab-95abd5cd37a9" />

how to add our code from local to remote repo-  
git add .  - this adds our code to index  
git commit -m "our message" - this adds our code to remote repo  
git push branch_name  

<img width="661" height="286" alt="image" src="https://github.com/user-attachments/assets/6a9564c5-712c-4d8e-8c3d-7c4218a2a27a" />


distribution models  
<img width="603" height="210" alt="image" src="https://github.com/user-attachments/assets/c10233ee-0adb-4761-98b1-e1e3aabad1a7" />  

branches-  
stable branch-the tip of the branch is working  
unstable branch-the tip of the branch maybe working or not working  

<img width="563" height="254" alt="image" src="https://github.com/user-attachments/assets/8241f034-d1d9-4b5f-b689-f9edd924a06e" />  





















