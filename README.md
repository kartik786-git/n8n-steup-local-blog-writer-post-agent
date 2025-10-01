# How to setup n8n on locally with docker(gpu) & ollama. 

## Pull ollama image from docker.
<img width="2523" height="864" alt="image" src="https://github.com/user-attachments/assets/07189f7d-7822-40f1-bf95-f72cbf24d08e" />

## pull n8n image from docker.
<img width="2539" height="689" alt="image" src="https://github.com/user-attachments/assets/7a4daa4e-b3b0-4802-a048-d2bd1f157557" />

## create a new volumn name as n8n_data in docker. 
<img width="2529" height="1084" alt="image" src="https://github.com/user-attachments/assets/d4101861-4381-4a5d-bc22-4cc674cbe77f" />

## Create container for ollama with network name.
docker run -it --rm --name n8n --network ollama-network -p 5678:5678 -v n8n_data:/home/node/.n8n n8nio/n8n

## pull ollama model ie "ollama pull llama3.2"
<img width="2497" height="851" alt="image" src="https://github.com/user-attachments/assets/f7a0bd86-712c-4df0-805a-0b82a80941d2" />
<img width="2543" height="976" alt="image" src="https://github.com/user-attachments/assets/76844c63-82d0-419a-8905-4318f8f9dc23" />

## create n8n container with network additionally required time zone. you can get time zone from here. 
https://en.wikipedia.org/wiki/List_of_tz_database_time_zones#List

docker run -it --rm \\
 --gpus=all \
 --name n8n \
 -p 5678:5678 \
 -e GENERIC_TIMEZONE="Asia/Calcutta" \
 -e TZ="Asia/Calcutta" \
 -e N8N_ENFORCE_SETTINGS_FILE_PERMISSIONS=true \
 -e N8N_RUNNERS_ENABLED=true \
 -v n8n_data:/home/node/.n8n \
 --network ollama-network \
 docker.n8n.io/n8nio/n8n

<img width="2540" height="1385" alt="image" src="https://github.com/user-attachments/assets/a9ad47ae-0ab2-485f-802c-63cdb6c1b14b" />

## create workflow for blog post
<img width="1918" height="938" alt="image" src="https://github.com/user-attachments/assets/69f07987-4002-46fe-9707-ad08abb64d9e" />

## deployed workflow.
<img width="1900" height="969" alt="image" src="https://github.com/user-attachments/assets/d5ebdb0f-a97f-4ed6-8459-58807a8e34f1" />


 
