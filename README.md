# Downloading and running sonarqube in Docker

## How to use
- clone this repository in your local machine where docker is running
    ```bash
    git clone https://github.com/mechdeveloper/sonarqube-docker.git
    cd sonarqube-docker
    ```
- To spin up services defined in docker-compose.yml file
    ```bash
    docker-compose up
    ```
- Log in to <http://localhost:9000> with System Administrator credentials (login=admin, password=admin).
Once your server is installed and running, you may also want to [Install Plugins](https://docs.sonarqube.org/latest/setup/install-plugin/). Then you're ready to begin [Analyzing Source Code](https://docs.sonarqube.org/latest/analysis/overview/) .

- To stop the services
    ```bash
    docker-compose down
    ```

## Components defined in docker-compose.yml
1. networks
    - create bridge network in docker named sonarqube

2. volumes

   volumes helps prevent the loss of information when updating to a new version or upgrading to a higher edition

    - sonarqube_data
      - contains data files, such as the embedded H2 database and Elasticsearch indexes
    - sonarqube_logs
      - contains SonarQube logs about access, web process, CE process, and Elasticsearch
    - sonarqube_extensions
      - contains plugins, such as language analyzers

3. services
    - sonarqube
      - runs sonarqube:8.3.1-community docker image as a contianer in Docker


## Reference
- <https://docs.sonarqube.org/latest/setup/install-server/>
