# Local Deployment

:::info
These instructions have been tested on MacOS, Windows 10 and Ubuntu 22.04.

:::

## Setup & launch Airbyte

- Install `Docker Engine` and the `Docker Compose plugin` on your workstation \(see [instructions](https://docs.docker.com/engine/install/)\).
- After Docker is installed, you can immediately get started locally by running:

```bash
# clone Airbyte from GitHub
git clone https://github.com/airbytehq/airbyte.git

# switch into Airbyte directory
cd airbyte

# start Airbyte
./run-ab-platform.sh
```

- In your browser, just visit [http://localhost:8000](http://localhost:8000)
- You will be asked for a username and password. By default, that's username `airbyte` and password `password`. Once you deploy airbyte to your servers, be sure to [change these](/operator-guides/security):

```yaml
# Proxy Configuration
# Set to empty values, e.g. "" to disable basic auth
BASIC_AUTH_USERNAME=your_new_username_here
BASIC_AUTH_PASSWORD=your_new_password_here
```

- Start moving some data!

## Deploy on Windows

After installing the WSL 2 backend and Docker you should be able to run containers using Windows PowerShell. Additionally, as we note frequently, you will need `docker-compose` to build Airbyte from source. The suggested guide already installs `docker-compose` on Windows.


### Setup Guide

**1. Check out system requirements from [Docker documentation](https://docs.docker.com/desktop/windows/install/).**

Follow the steps on the system requirements, and necessarily, download and install the Linux kernel update package.

**2. Install Docker Desktop on Windows.**

Install [Docker Desktop](https://docs.docker.com/desktop/windows/install/) from here.

Make sure to select the options:

1. _Enable Hyper-V Windows Features_
2. _Install required Windows components for WSL 2_
   when prompted. After installation, it will require to reboot your computer.

**3. Enable WSL2, Install Ubuntu 20.4, Windows Terminal, Upgrade Python to version 3.9, Install Git, Docker Desktop, and Docker Compose.**

**4. Enable Docker to run correctly on WSL by checking the “Use the WSL two-based engine” and “Enable Kubernetes” checkboxes in the Docker settings.**

**5. Navigate to your Airbyte directory in the terminal and run docker-compose up to spin up all Airbyte containers.**

**6. After the Airbyte banner shows up in the log, navigate to localhost:8000 to access the Airbyte UI.**

For more detailed instructions, please refer to the Airbyte Video Tutorial on YouTube: <https://www.youtube.com/watch?v=CtuU9Oi-6O8>

```bash
git clone https://github.com/airbytehq/airbyte.git
cd airbyte
bash run-ab-platform.sh
```

- In your browser, just visit [http://localhost:8000](http://localhost:8000)
- You will be asked for a username and password. By default, that's username `airbyte` and password `password`. Once you deploy airbyte to your servers, be sure to [change these](/operator-guides/security).
- Start moving some data!
## Troubleshooting

If you encounter any issues, just connect to our [Slack](https://slack.airbyte.io). Our community will help! We also have a [troubleshooting](../troubleshooting/on-deploying.md) section in our docs for common problems.
