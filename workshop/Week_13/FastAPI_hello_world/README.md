<p align = "center" draggable=”false” ><img src="https://user-images.githubusercontent.com/37101144/161836199-fdb0219d-0361-4988-bf26-48b0fad160a3.png"
     width="200px"
     height="auto"/>
</p>


# <h1 align="center" id="heading">FastAPI Hello World</h1>


For this session, our goal will be to run a health check endpoint in FastAPI, launch our local server, and hit the `docs` endpoint.

You will learn how to:
- Write FastAPI endpoints
- Deploy it on a local server

## Let's Get started!

#### Setting up the Respository

<details>
     <summary>Click to Expand</summary>

  ###### Creating our Repository

  Login to GitHub and navigate to your repositories.

  <p align="center">
    <img src="https://user-images.githubusercontent.com/37101144/162326947-3bfb4451-9854-41e8-9014-a02ed1322d66.png">
  </p>



  When viewing the respository page, click on `New` and proceed to create your repo.

  <p align="center">
    <img src="https://user-images.githubusercontent.com/37101144/162327218-e1429ab2-2b24-4822-95bf-4411c2eb4a84.png">
  </p>
  <hr>

  ###### Filling Respository Details

  Create the repository by inputting the following:
  * `Repo name`
  * `Repo description`
  * Make repo `public`
  * Add a `README`
  * Add `.gitignore` (Python template)
  * Add `license` (choose MIT)

  Then click `Create Repository`.

  <p align="center">
    <img src="https://user-images.githubusercontent.com/37101144/162327471-262a0931-c188-4976-8185-e70c4d108f71.png">
  </p>

</details>

#### Cloning our Repository

<details>
     <summary>Click to Expand</summary>

  <br>

  Launch `Ubuntu` from our `Terminal App` (or your preferred terminal that has `Conda` configured)
  <br>

  ![WindowsTerminal](https://user-images.githubusercontent.com/72572922/160048214-37f08855-8b29-4c13-9d25-e0f69806f752.jpg)

  In Ubuntu, create a new folder called `my_container` and `cd` into it.

  ``` bash
  mkdir my_container && cd $_
  ```

  Copy the link from your newly created repository and clone it on your machine using `git clone [your repository link]` and `cd` into the repository.

  ![1](https://user-images.githubusercontent.com/37101144/166337467-56abb8ba-13ad-4599-af90-8a5dcf20ec77.png)

  ```bash
  git clone [your repository link]
  ```

  ```bash
  cd [repo name]
  ```

</details>


#### Setting up our Environment

<details>
    <summary>Click to Expand</summary>

  <br>
  Create a `conda` virtual environment

  ``` bash
  conda create -n fastapi_env python=3.8 pip
  ```

  Activate the environment

  ``` bash
  conda activate fastapi_env
  ```

  Install `FastAPI`

  ``` bash
  pip install fastapi
  ```

  Install `uvicorn`

  ``` bash
  pip install uvicorn
  ```

  Save all the `pip` requirements

  ``` bash
  pip freeze > requirements.txt
  ```

  Use `touch` to create a `main.py`

  ```bash
  touch main.py
  ```
  Open up the file in VS Code using Terminal

  ```bash
  code .
  ```

</details>



#### Write the Health Check endpoint
<details>
     <summary>Click to Expand</summary>

  Click on `main.py` on the left side bar. In `main.py` import FastAPI

  ``` python
  from fastapi import FastAPI
  ```
  Instantiate FastAPI server object

  ``` python
  app = FastAPI()
  ```

  Create a `get` endpoint called `/health`. See [here](https://fastapi.tiangolo.com/tutorial/first-steps/).
  ``` python
  @app.get("/health")
  def health():
      return "Service is online."
  ```

  Click on `View` in the title bar up top and then click `Terminal`. It's time to launch the server locally. Inside the terminal, run your application using `uvicorn` on port `8000`

  ``` bash
  uvicorn main:app --port 8000
  ```

  Commit changes and push up to your Git repo

</details>

#### Resources
* https://fastapi.tiangolo.com/tutorial/first-steps/
* https://fastapi.tiangolo.com/tutorial/body/
