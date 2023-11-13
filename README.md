# GitLab With Docker

This Docker Compose configuration allows you to easily set up a GitLab instance using the GitLab Enterprise Edition image. Follow the steps below to get started.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Getting Started

1. Clone this repository:

    ```bash
    git clone https://github.com/kahnu044/gitlab-with-docker
    ```

2. Navigate to the project directory:

    ```bash
    cd gitlab-with-docker
    ```

3. Create necessary directories(if not present) for GitLab and give them permission:

    ```bash
    mkdir -p gitlab/config gitlab/logs gitlab/data
    sudo chmod -R 777 gitlab/
    ```

4. Deploy GitLab using Docker Compose:

    ```bash
    docker-compose up -d
    ```

5. Access GitLab in your browser:

    [https://code.developernoob.in](https://code.developernoob.in)

6. Retrieve the initial root password:
    Find the the docker container id by running the following command
    ```bash 
    docker ps
    ```
    Change the container name `gitlab-with-docker_web_1` to `<your container name>`

    ```bash
    sudo docker exec -it gitlab-with-docker_web_1 grep 'Password:' /etc/gitlab/initial_root_password
    ```

    Use the displayed password to log in as the root user.

7. Log in to GitLab:

    - URL: [https://code.developernoob.in](https://code.developernoob.in)
    - Username: `root`
    - Password: Use the password retrieved in step 7.

## Customization

- Adjust the `external_url` in the `GITLAB_OMNIBUS_CONFIG` environment variable to match your desired GitLab URL.
- Explore additional GitLab configuration options in the [official documentation](https://docs.gitlab.com/ee/administration/omnibus.html).

## Notes

- Ensure that ports 80, 443, and 2222 on your server are accessible.
- Remember to change the initial root password after the first login.
