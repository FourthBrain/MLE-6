# Testing in Python

At certain point in your career as a machine learning engineer, you will need to write functions, or even modules that are not readily offered by common packages. It is critical to detect bugs and inconsistencies in the early stage of the development. We here offer a *gentle* introduction to testing in Python (read [Test Driven Devlopment (TDD)](https://testdriven.io/test-driven-development/), a methodology in software development, think of it as "start from the end"), to set you up for being a better engineer!

In this session, you will write unit tests, where a test case is the individual unit of testing and checks for a specific response to a particular set of inputs, test it using `pytest`, and practice [Git Feature Branch Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow). 

## Objetives
By the end of the session, you will 
- Know how to write unit tests in Python
- Know how to run tests using `pytest`
- Know what type hints are
- Feel more comfortable with collaborating as a team via GitHub

## Submission
Submit the link to the repo you worked on to Canvas (Bill's repo).

## Tasks
Start with the repo created last week. Decide who assumes Apple / Bill's role. For the first two tasks, most of the commands are provided. You need to complete the commands whenever you see "YOU DO IT". For the latter tasks, you will see the instructions are less detailed and you will write the code. 

### Task 1: Install `pytest` 
Each of you shall complete this task. To install `pytest`, activate the environment created last week, then run
```bash
pip install -U pytest # or pip3 install -U pytest
```

Explain to your teammate what the flag `-U` does during installation. 


### Task 2: Add tests
Say both work off Bill's repo. Bill adds Apple as collaborator, and Apple is the driver for this task when Bill is the observer / navigator:

1. Clone Bill's Repo and `cd` into the directory.
    ```bash
    git clone git@github.com:[bill handle]/naive-addition.git
    cd naive-addition
    git status # make sure you are on the branch `main`
    ```
1. Create a new branch `add-tests` and make sure you are on that branch.
    ```
               # YOU DO IT: start a new branch called "add-tests"
    git status # check and make sure you are on branch "add-tests"
    ````

1. Create a new folder `tests`. YOU DO IT. Use command line.  

1. Create a new file `tests/test_add.py`. YOU DO IT. Use command line.

    After you are done, your root directory should look like this:
    ```
    .
    ├── .git
    ├── .gitignore
    ├── LICENSE
    ├── README.md
    ├── requirements.txt
    ├── src
    │   ├── __init__.py
    │   └── add.py
    └── tests
        └── test_add.py
    ```
1. Add the following into `test_add.py` and save the changes:
    ```python
    from src.add import add
    def test_add():
        assert add(1) == 101
    ```
1. Run the test. 

    ```bash
    PYTHONPATH=. pytest tests/test_add.py
    ```
    `PYTHONPATH=.` tells Python to search functions / modules in the current directory and is required to run the test successfully (you shall run `pytest tests/test_add.py` and inspect the output). Read [PYTHONPATH](https://docs.python.org/3/using/cmdline.html) if you are not familiar with it. 

    The output shall look somthing similar to this
    ![](../img/output-run-single-test.png)

    What do you see if you run `PYTHONPATH=. pytest`?
    
1. Make sure there's no errors at each step then push the changes to the remote branch. 
    ```bash
    git status # check if there are any changes
    git add tests/test_add.py
    git status # check status again
    git commit -m ## YOU DO IT: complete the command
    git push origin add-tests
    ```
1. Create a pull request on GitHub.
1. Review your own PR.
1. Bill reviews the PR, approves it, merges it into the `main` branch.
1. Both Apple and Bill pull the recent changes from the remote repository.

### Task 3: More tests 
We would like to relax the function `add`, not to limit its parameters to integers; e.g., currently `x: int` indicates that `x` be an integer (it is a naive example as you see the current function won't complain if inputs are arrays). Following TDD, we want to write tests before updating the function. 

Bill is the driver. Notice that both are working on the same feature, i.e., adding tests, so instead of creating a new branch, Bill works on the `add-tests` branch.

1. Check out branch `add-tests` that Apple created.
2. Add first test cases in `test_add.py` that first argument takes in a numpy array and check if the summation is as expected (keep your test case simple).
3. Run test using `pytest` and make sure all tests pass. 
4. Commit your changes.
5. Add second test cases where both arguments take numpy arrays; run test and make sure all tests pass, and commit your changes.
6. Add third test cases where both arguments are `str`, e.g., `add("fourth", "Brain") == "fourthBrain"`; run test and make sure all tests pass, and commit your changes.
7. Push your changes to the remote branch.
8. Create a pull request on GitHub.
9. Review your own PR.
10. Apple reviews the PR, approves it, merges it into the `main` branch.


### Task 4: Update Function and README
This task is different from the previous ones. After reading the instructions together, Apple and Bill work on different features individually (this is the scenario where you collaborate on your capstone project as a team). When the feature is finished, each creates merge requests, reviews each other's PR, and merges them into the `main` branch. NEVER commit code if there are errors. In the very end, make sure you local repo is sync with the remote repo.

Consider the following two features:
#### Task 4a: Update Function (Apple)
1. Remove the type hint from function `add`.
2. Update the docstring to reflect changes.
3. Push the changes to the remote feature branch.
4. Create a PR on GitHub and review your own PR.
5. Apple reviews Bill's PR, approves it, merges it into the `main` branch, and deletes the branch.
6. Both Apple and Bill pull the recent changes from the remote repository.

#### Task 4b: Update README (Bill)
1. Update the README to reflect changes.
2. Push the changes to the remote feature branch.
3. Create a pull request on GitHub and review your own PR.
4. Bill reviews Apple's PR, approves it, merges it into the `main` branch, and deletes the branch.
5. Both Apple and Bill pull the recent changes from the remote repository.

#### Task 4c: Update .gitignore (Cathy)
If there is a third member in the team, update the file `.gitignore` to ignore the files that are not needed. For example, for mac users, add `.DS_Store` to the `.gitignore` file following the workflow listed above.

### [Optional] Task 5: Design a New Feature and Incorporate it
This task is more open-ended and do it if time permits it. Design a new feature to expand the `naive-add`, it can be a new function and its test(s), or add error handling to the existing function, or add [doctest](https://docs.python.org/3/library/doctest.html) to the current function and [test it](https://doc.pytest.org/en/latest/how-to/doctest.html), just to name a few. 

## Note / References
- There are other test suites for Python, such as [`unittest`](https://docs.python.org/3/library/unittest.html) and [`nose2`](https://docs.nose2.io/en/latest/). We use [`pytest`](https://docs.pytest.org/en/6.2.x/getting-started.html) for its simplicity, readability, and flexibility. More details in [The Cleaning Hand of Pytest](https://blog.daftcode.pl/the-cleaning-hand-of-pytest-28f434f4b684). 

- We started with functional programming here. As the application / module you develop gets complicated, OOP will serve better. Check out some examples offered by [`pytest`: getting started](https://docs.pytest.org/en/6.2.x/getting-started.html).

- In this article [Python Type Checking (Guide)](https://realpython.com/python-type-checking/), you will find what dynamic, static, and duck typings are, pros and cons adding types to your code, etc. 

- [Cheat Sheet](https://mypy.readthedocs.io/en/stable/cheat_sheet_py3.html), more details are in the documentation on module [`typing`](https://docs.python.org/3/library/typing.html)

- If you are curious how to vaildate types in Python, [`mypy`](https://mypy.readthedocs.io/en/stable/getting_started.html) is a popurlar tool.
    
    