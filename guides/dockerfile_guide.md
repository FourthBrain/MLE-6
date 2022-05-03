<p align = "center" draggable=”false” ><img src="https://user-images.githubusercontent.com/37101144/161836199-fdb0219d-0361-4988-bf26-48b0fad160a3.png"
     width="200px"
     height="auto"/>
</p>


# <h1 align="center" id="heading">Create a Dockerfile in your Python App Project</h1>

<br>


### Build and Run a Standard Template for a Dockerfile

<details>
  <summary>Click to Expand</summary>

<br>

<b>Dockerfile</b>

This is an example of a basic Dockerfile. A Dockerfile is a set of instructions for writing a Docker image. See the next section in `Custom Template for a Dockerfile using Ports` for a detailed explanation of each line.

``` Bash
FROM python:3

WORKDIR /usr/src/app

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD [ "python", "./your-daemon-or-script.py" ]
```
<i> Credits:  [DockerHub](https://hub.docker.com/_/python)</i>


<b>Building the Docker Image</b>

You can then build the Docker image from your files:
``` bash
$ docker build -t my-python-app .
```


<b>Running the Image in a Container</b>
  
You can then run this image. When you run an image, it's ran in a container.
```bash
$ docker run -it --rm --name my-running-app my-python-app
```

</details>




### Build and Run a Custom Template for a Dockerfile using Ports

<details>
  <summary>Click to Expand</summary>

<br>

<b>Dockerfile</b>

Grab an image from [DockerHub](https://hub.docker.com/_/python)
``` bash
  FROM python:3.8.1-slim
```

Open the desired ports inside the container
``` bash
  EXPOSE 8000
```

State the working directory inside the container
``` bash
  WORKDIR .
```

Copy files from source directory (first `.`) to destination directory (second `.`)
``` bash
  COPY . .
```

Install modules from `requirements.txt` file
``` bash
  RUN pip install --no-cache-dir -r requirements.txt
```

Declare the entry point. This is the command your container will execute when it starts.
``` bash
  CMD ["uvicorn","--host", "0.0.0.0", "--port", "8000", "src.main:app" ]
```

<b>Building the Docker Image</b>
  
You can then build the Docker image from your files:

``` bash
docker build -t fastapi-demo .
```

<b>Running the Image in a Container</b>
  
You can then run this image. When you run an image, it's ran in a container. In this case we're connecting port `8000` on our deployment machine (left of the `:`) with port `8000` (right of the `:`) in our container.

``` bash
docker run -dp 8000:8000 fastapi-demo
```
</details>

#### Resources
[Docker Cheat sheet](https://www.docker.com/wp-content/uploads/2022/03/docker-cheat-sheet.pdf) \
[Docker Ultimate Guide](https://github.com/wsargent/docker-cheat-sheet/blob/master/README.md)
