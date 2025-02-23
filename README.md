# proving_it_stack

This repo was part of a LinkedIn article I wrote to help me remember, all the important stuff I learned from the ProveIt! 2025 conference hosted by 4.0 Solutions.

Feel free to fork and use it as a template to get you started on your Digital Transformation journey and building a Proof of Concept!

PLEASE NOTE: I chose NOT to add a database to this configuration as most users already have one available and data storage is a very opinionated thing.

## First we need

- A bare-metal Linux box installed with the latest Ubuntu (LTS) release running on something with around ~8-10 cores (or more) and 16GB of RAM minimum. (about $250-500 on craigslist)
- [Install docker on the box.](https://docs.docker.com/desktop/setup/install/linux/)
- A ChatGPT/Google Gemini subscription. (about $20/month, please note this tutorial uses ChatGPT, so your mileage may vary with Gemini)

## Setup environment variables

- See the `env` folder for where to place Ignition Maker License keys, usernames and passwords for the apps.
- Once you get keys and passwords saved it's a good idea to add that folder to the `.gitignore` to prevent leaking credentials when making commits to version control.

## Setup docker/portainer persistant container volumes

This just ensures that data is save in folders between restarts and stops. Please note that Node-RED is the only container that doesn't have a physically bound folder, due to permission errors.

### Start the containers

*Fun fact: note the space between "docker compose" makes a HUGE difference as running docker-compose is not the same version of the command!*

```bash
docker compose up -d
```

### Stop the containers

```bash
docker compose down
```

### Check the ports in the browser

[http://localhost:9000] #Portainer (Community)

[http://localhost:1880] #Node-RED

[http://localhost:8088] #Ignition (Maker Edition)

[http://localhost:8080] #HiveMQ-Edge

### Recommended next steps

- Install Ignition Designer (Packaged with Ignition)
  - Don't forget to grab your Ignition Maker's key from their site!
- Install the [MQTT Engine module from Cirrus link](https://inductiveautomation.com/downloads/third-party-modules/8.1.45)
- Sign-up for [Digital Factory Mastermind Program](https://www.iiot.university/digital-mastermind)
- Start building your very own Unified Namespace and IIoT 4.0 web apps!

### Cool stuff I use

The following docker plugins for VSCode:

- [Microsoft's Docker plugin](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
- [Microsoft's Dev Container Plugin](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

Other stuff:

- [Guake](https://github.com/Guake/guake)
- [Node-RED UI Builder](https://github.com/TotallyInformation/node-red-contrib-uibuilder)
- [Odoo](https://github.com/odoo/odoo)
  