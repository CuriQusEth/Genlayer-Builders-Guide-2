# Genlayer-Builders-Guide-2

Genlayer-Builders-Guide-2
Requirements:
docker
wsl
vsCode
Rabby wallet extension
Node.js (v18+) & npm
Python (v3.10+)
Note: we will be deploying on studionet
step 1
install genlayer cli
  npm install -g genlayer
create project folder
  mkdir yourProjectName
navigate to project folder

  cd yourProjectName
create contracts

  mkdir contracts
mkdir contracts and frontend
step 2
initialize genlayer blockchain with your docker
  genlayer init
git init
you will be asked to select LLM type and provide API keys

use heurist ai
visit heurist
use "genlayer" as ref code to get free api credits
get your credits and use it to run the initialization
if this does not work, try the following;
run
  docker pull postgres:17-alpine
if you still encounter issues, pull the images from docker manually
manually pull images
after getting thr initialization started, run

  genlayer up
to start up the blockchain

step 3 creating and deploying your contract
to create your own contract please read the genlayer docs or you can feed the genlayer docs to any ai and ask it to write a smart contract depending on what you intend to create

creating your contract file
i believe you must have your smart contract written down already

in your terminal, run
  code .
image
this opens up your project folder inside vsCode editor (from here you can make simple copy and paste edits to your project files)

right click on the contracts folder and create a new file (name it according to your project, eg, fight.py since genlayer contracts are written in python)
paste you contract code into the file and save
set at studionet
go back to your terminal and run

  genlayer network set studionet
create studionet deployer
create deployer account
  genlayer account create --name studio-deployer
genlayer account use studio-deployer
you will be asked to setup an encryption key (password)

deploy contract to genlayer studionet
  genlayer deploy --contract contracts/yourContractName.py
enter password to deploy, copy your contract address (you will make use of it in setting up your .env file)

step 4 creating the frontend logic
create a vue frontend template
run, in the project folder

  npm create vite@latest frontend -- --template vue-ts
move into frontend folder,

  cd frontend
install vue

  npm install
install genlayer SDK

  npm install genlayer-js
create environment
create a .env file inside the frontend folder and input this below

create  env
  VITE_CONTRACT_ADDRESS=0xYOUR_COPIED_ADDRESS
replace 0xYOUR_COPIED_ADDRESS with the contract address deployed earlier

editing App.vue and styles.css
navigate to frontend/src/styles.css and delete everything inside the file

image
your main frontend code will be stored inside App.vue
if you cannot write that seek help from an ai
image
after filling in your frontend, save it

run the frontend
in your terminal, make sure your are inside the frontend directory run,

  npm run dev
image
it should provide a localhost address like this [http://localhost:5173/] that you can open on your browser

image
NOTE; test to see if everything works as you want, then proceed to pushing into github
create a github repository
visit github sign in with your account and create a repository

important: do not toggle on read.me, gitignore or license when creating your project github repo
create a gitignore file
make sure you are in the projects main folder then run,

  node_modules
.env
dist
__pycache__
create gitignore
set your email
run this, anything works here lol

  git config --global user.email "kek@example.com"
set username chuks for git
set username
run,

  git config --global user.name "anyname"
add to main repo and final commit
run

  git init
git add .
git commit -m "i am doing my best kek"
make commit changes final
you can replace "i am doing my best kek" to actually anything

push to github
run,

note; replace the first url with the url of your github repo
e.g i replaced mine to (https://github.com/CuriQusEth/Genlayer-Builders-Guide-2)

 git remote add origin https://github.com/YOUR_USERNAME/repositoryname.git
git branch -M main
git push -u origin main
push to github
you will be asked for your github username and password

input your username
for password, create a personal access token in your github
how to create personal access token:
go to your github settings
navigate to developer settings
then create personal access token
use tokens (classic)
select no expiration
name it as "vercel"
tick only "repo"
scroll down and generate token
copy token and paste as the password on your terminal
enter
this should push to github and you can see it on you github
pat
deploy on vercel
visit vercel
signin with your github
click on add new and select project
you should see the latest github repos on your github
image
select your project repo and import
on root directory click edit and choose frontend
edit and deploy on vercel
open up environment variables, input; VITE_CONTRACT_ADDRESS in key section and your contract address in the value section

finally, you can deploy

making it public
after deployment, go to dashboard and locate your newly deployed project
click on the three dots and select settings
damn
go to deployment protection and turn vercel authentication off
then save
you can now share ypur project with youe friends
h,mm
GUIDE MADE BY CHUKSDAKINGS, X
