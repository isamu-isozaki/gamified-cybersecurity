# gamified-cybersecurity

The goal of this project is for users to be able to learn cyber security in hackthebox like environment. This project is divided into 5 main parts.

1. Frontend: Here, users will be be interacting with a terminal to try to solve a puzzle. We also plan to have interactions with a llm here to assist in learning. For this, we plan to use a react js app with the react-terminal package.
2. Vulnerable machines: These will be randomly generated vulnerable docker images. One goal we have is to make the game similar to a rogue like so we will want to randomly generate these images. However, if every user will be able to randomly spin up a dockerfile in the backend, that will be a scalability nightmare. So the current plan is to have 4 randomly generated dockerfiles which will rotate every day or so. That way there will be no need to spin up new images.
3. Backend: The main task of the backend is connect the frontend to the ssh logs of the vulnerable machine and also connect the llm with the frontend.
4. LLM: This LLM will be inspired by pentest gpt and will be the main part I will be working on. My goal is to have a minimal "teacher" model which can help with pentesting while not providing answers and not hallucinating.
5. Attacker machine: These will be an attacker machine to attack vulnerable containers

As the project becomes more complicated, I suspect we will need to include celery and redis for scalability but for now this should do. I also added a postgres dataset in docker-compose just for future use. THe main idea for the dataset is used to correct user commands for future improvement

## How to run
```
git clone https://github.com/isamu-isozaki/gamified-cybersecurity-frontend.git frontend
git clone https://github.com/isamu-isozaki/gamified-cybersecurity-backend.git backend
git clone https://github.com/isamu-isozaki/gamified-cybersecurity-ai-server.git ai-server
```
To update do
```
cd frontend
git checkout main
git pull origin main
cd ../backend
git checkout main
git pull origin main
cd ../ai-server
git checkout main
git pull origin main
cd ..
```
Then, do
```
docker-compose up
```
I recommend commenting out the frontend part of docker-compose and just do
```
cd frontend
yarn
yarn start
```
and if you are developing backend, you can just do
```
npm install
npm run dev
```
