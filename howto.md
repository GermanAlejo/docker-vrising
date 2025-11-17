# Installation & Usage

How to install *TrueOsiris/docker-vrising* in our server and run it

## Installation & Set up

### Prerequisites

We need ssh and docker in the server already installed

### Installation

1. clone repo

```git
git clone https://github.com/GermanAlejo/docker-vrising.git
```

This is a fork of *TrueOsiris/docker-vrising* but with the configuration changed for out own server.

2. Create the folders in the server.

Inside the folder with the docker project create 2 folders, server & persistance

- server: folder containing all server files needed to run the vrising server
- persistance: folder containing configuration files and save files

3. Edit docker-compose.yml

*This step can be skipped if the server did no change, as in this repo is already set up*
Edit the docker-compose.yml file if needed, we should only need to edit 2 properties:

- environment: set our timezone and servername
- volumes where we specified the path to the folders we created previously

4. Open ports

The hosting server need to open and fordward ports: 9876/UDP & 9877/UDP.

5. Run the server

```bash
docker‑compose up -d
```

After the first launch, check /home/vrising/persistentdata/Settings/ServerHostSettings.json to configure passwords, visibility, RCON, etc.

You will likely need sudo permissions

#### Use existing save:

If we want to use a save already existing we will need to copy the folder in:
**AppData/LocalLow/Stunlock\ Studios/VRisingServer/Saves/world1**

And replace it in the server in the folder persistance:
/your/host/vrising/persistentdata/Saves/world1

Also remember to replace the name of the world in **/your/host/vrising/persistentdata/Settings/ServerHostSettings.json** if needed

### Usage

Use like a normal docker container:

```

docker restart vrising
docker start vrising
docker stop vrising

docker logs -f vrising # Para ver los logs

docker-compose down
docker-compose up -d
```

ver logs: docker logs -f vrising

---

## Connect

How to play and log into the server:
1. Inside the game go to : play -> online -> hosted servers -> direct connect
2. Write ip Address and password

---


