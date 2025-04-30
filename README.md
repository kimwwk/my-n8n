# command to run

## one time setup

```sh
curl -sSL https://ngrok-agent.s3.amazonaws.com/ngrok.asc \
  | sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null \
  && echo "deb https://ngrok-agent.s3.amazonaws.com buster main" \
  | sudo tee /etc/apt/sources.list.d/ngrok.list \
  && sudo apt update \
  && sudo apt install ngrok

ngrok config add-authtoken $token
# Get the token from ngrok
# Authtoken saved to configuration file: ~/.config/ngrok/ngrok.yml
```

## to start the workflow

```sh
ngrok http 5678

# update the WEBHOOK_URL in docker compose yml config
docker compose up -d

# and then turn on the workflow of rental-repost
```
