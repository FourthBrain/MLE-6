<p align = "center" draggable=”false” ><img src="https://user-images.githubusercontent.com/37101144/161836199-fdb0219d-0361-4988-bf26-48b0fad160a3.png"
     width="200px"
     height="auto"/>
</p>


# <h1 align="center" id="heading">AWS "Hello World"</h1>

For this assignment, our goal will be to run python on a cloud server on Amazon Web Services (AWS). We will essentially be using AWS as a virtual machine. The AWS cloud server we'll be using today is called Elastic Compute Cloud (EC2).

We'll first start by creating a repository and modifying it on our local machine. We'll then launch an EC2 instance (server) with a specific configuration so we can access it publicly. From there, we'll add our files that we modified to server and test it.


### Setting up the Repository
<details>
     <summary><b>Click to Expand</b></summary>

##### Creating our Repository

Login to GitHub and navigate to your repositories.

<p align="center">
  <img src="https://user-images.githubusercontent.com/37101144/162326947-3bfb4451-9854-41e8-9014-a02ed1322d66.png">
</p>



When viewing the respository page, click on `New` and proceed to create your repo.

<p align="center">
  <img src="https://user-images.githubusercontent.com/37101144/162327218-e1429ab2-2b24-4822-95bf-4411c2eb4a84.png">
</p>
<hr>

##### Filling Respository Details

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








### Cloning our Repository
<details>
     <summary><b>Click to Expand</b></summary>

<br>

Launch `Ubuntu` from our `Terminal App` (or your preferred terminal that has Conda configured)
<br>

![WindowsTerminal](https://user-images.githubusercontent.com/72572922/160048214-37f08855-8b29-4c13-9d25-e0f69806f752.jpg)

In Ubuntu, create a new folder called `week3_assignment` and `cd` into it.

![image](https://user-images.githubusercontent.com/72572922/164912163-3b67f2f0-ff94-419b-9313-1ab6c44ed76a.png)

Copy the link from your newly created repository and clone it on your machine using `git clone [your repository link]` and `cd` into the repository.

![image](https://user-images.githubusercontent.com/72572922/164912311-f1c3856a-4777-482c-b567-470fec83ebc8.png)

![image](https://user-images.githubusercontent.com/72572922/164912559-7cf0eba2-5d7d-419c-bda6-bc7baaec3e3a.png)

</details>








### Creating and Modifying our `Main.py`
<details>
     <summary><b>Click to Expand</b></summary>

<br>

![image](https://user-images.githubusercontent.com/72572922/164912613-1d0bbda1-5681-4215-97ca-ba178dd9dca1.png)

Click on `main.py` on the left side bar. Add the following code block and save the file.

``` python
Print("Hello AWS World!")
```
![image](https://user-images.githubusercontent.com/72572922/164912678-b28ea859-7fb6-46f9-b2e0-d22b0cecb53c.png)

### Updating the Repository with our Modified File

<br>

Click on the version control button on the left side bar.

![image](https://user-images.githubusercontent.com/72572922/164912767-412e7ea3-483c-4abd-8a80-f8bf72a9c919.png)

Click on the `+` button to stage the `main.py` file.

![image](https://user-images.githubusercontent.com/72572922/164912818-3eccfa41-572c-434e-a244-3cadde42290a.png)

Click the check mark button to commit the changes.
![image](https://user-images.githubusercontent.com/72572922/164912901-98fdfcc9-21e6-4dc7-8f3d-0477fa76fc34.png)

Click on `Save All & Commit`

![image](https://user-images.githubusercontent.com/72572922/164913064-3fd0b27f-bd4c-4c3e-ae49-6d71132b2df4.png)

Enter any description for the commit and hit `enter`.

![image](https://user-images.githubusercontent.com/72572922/164913127-2e379a66-4880-4098-bbe3-f1d02ae9c3f6.png)

Click on `Sync Changes` on the left side bar.

![image](https://user-images.githubusercontent.com/72572922/164913186-5146ff20-283b-4af5-96b7-c332af0025b4.png)

Click on `View` and then `Terminal`
![image](https://user-images.githubusercontent.com/72572922/164913552-d67a40cb-9aed-4850-8237-cd907002b683.png)

![image](https://user-images.githubusercontent.com/72572922/164913618-9a07fd0c-87c2-4fc6-8f79-be866761e020.png)

</details>


















### Launching an AWS Instance
<details>
     <summary><b>Click to Expand</b></summary>

Go to `https://aws.amazon.com/ec2/` and sign in to the console on the top right.

![image](https://user-images.githubusercontent.com/72572922/164913952-b7f46605-5c2c-4950-9383-82e0f66c5a6f.png)

Log in with your information

![image](https://user-images.githubusercontent.com/72572922/164914070-7accba62-2ace-4b9d-bc30-2405f0d904cd.png)

Click on `EC2`

![image](https://user-images.githubusercontent.com/72572922/164914324-c65c778e-d9d5-41b6-814e-ff9738d26173.png)

Click on `Instances`
![image](https://user-images.githubusercontent.com/72572922/164914373-e46c5ad0-f48f-4a49-8eb0-6708727504d3.png)

Click on `Launch Instances`
![image](https://user-images.githubusercontent.com/72572922/164914415-3ec7d438-9aa1-4e4d-9aba-794f7f91c6d7.png)

Give a unique name to your EC2 Instance
![image](https://user-images.githubusercontent.com/72572922/164914471-2dc15667-1ec5-4aab-abc5-1fa76d618c57.png)

![image](https://user-images.githubusercontent.com/72572922/164914471-2dc15667-1ec5-4aab-abc5-1fa76d618c57.png)

Choose your keypair. If you haven't created one yet, please create one and it will download a `.pem` file. You will use this key to access your EC2 instance using SSH.

![image](https://user-images.githubusercontent.com/72572922/164914693-18868de2-07a7-47d1-ad3a-8781fb75ac4f.png)

![image](https://user-images.githubusercontent.com/72572922/164914525-98bb8c61-833a-49f8-a260-076697289d4d.png)

Click on the `Edit` button under network settings.

![image](https://user-images.githubusercontent.com/72572922/164914793-83190741-506e-4d28-9f46-adba86f4a5b2.png)

Change the `VPC` to `Project VPC`

![image](https://user-images.githubusercontent.com/72572922/164914833-586f5f8b-1358-4538-a7d1-aa85f6271851.png)

![image](https://user-images.githubusercontent.com/72572922/164914852-437c7742-c16d-43ed-ad5b-84ff3fda4bac.png)

Click on `subnet mask` and choose the `PUBLIC east` `1a` or `1b`.

![image](https://user-images.githubusercontent.com/72572922/164914896-b542674a-a1b5-4b8c-992a-c8700afedb98.png)

![image](https://user-images.githubusercontent.com/72572922/164914884-92ac6bcf-0fe4-4844-b2e3-7cd2277ef01c.png)

Click on `Auto-assign Public IP` and choose `Enable`

![image](https://user-images.githubusercontent.com/72572922/164915082-e246b7ca-742f-491b-8ea2-a9c80ef4f8bf.png)


In the `Security Group Rules`
- select `Custom TCP`
- set `Port range` as `8000`
- set `Source type` as `Custom`
- set `Source` as `0.0.0.0/0`
- set description as `Public IP port`

![image](https://user-images.githubusercontent.com/72572922/164915174-83cee798-8952-4877-87bd-f25443248075.png)

It should look like this

![image](https://user-images.githubusercontent.com/72572922/164915458-5c2db6d3-918a-4fc5-a01f-c9d80f1dbef8.png)

We will now add a second security group rule to allow us to access EC2 using SSH.

![image](https://user-images.githubusercontent.com/72572922/164915509-fd542af7-d829-4831-a7f5-77858f3535f0.png)

In this security group rule, we will set the following:
- select `Custom TCP`
- set `Port range` as `22`
- set `Source type` as `Custom`
- set `Source` as `0.0.0.0/0`
- set description as `SSH to Desktop`

![image](https://user-images.githubusercontent.com/72572922/164915583-f9b7b836-9568-4973-b7d1-8bfbf9e3f492.png)

We can now launch our instance. Click `Launch Instance`.

![image](https://user-images.githubusercontent.com/72572922/164915629-c3b84572-3be9-4bdc-bc6c-d404f6b3cf8b.png)

Click on `View all instances`

![image](https://user-images.githubusercontent.com/72572922/164915673-54850a0e-4e56-47d4-ad77-2616ffba5ff1.png)

Click on your instance ID. If you don't see your instance, simply refresh the page.

![image](https://user-images.githubusercontent.com/72572922/164915737-a9bbfe33-3903-4ac1-8206-a372a1372175.png)

Click on the instance id corresponding to your instance name

![image](https://user-images.githubusercontent.com/72572922/164915766-bc1c3f3a-30f1-42b5-9077-6fd9a242f82e.png)


Wait until the instance state is `running`. If it's not running, feel free to refresh the page. Then click `Connect`

![image](https://user-images.githubusercontent.com/72572922/164915808-43d71b78-ddc6-4244-805b-df7e4d102a1c.png)

Click on `SSH Client`. There, you will find instructions on how to connect using the `.pem` file you downloaded earlier.

![image](https://user-images.githubusercontent.com/72572922/164915892-548daff5-c460-4ab0-b866-d30757e857c7.png)

</details>












### Accessing the EC2 Instance using SSH
<details>
     <summary><b>Click to Expand</b></summary>

Let's jump back to VS Code with our `Terminal` window open inside.

![image](https://user-images.githubusercontent.com/72572922/164916200-d15b75cd-f20d-4d4f-912a-3ff58105d8e6.png)



`cd ..` up one folder and copy the `.pem` file from your download directory into the current folder using the following command:
```bash
cp -R DIRECTORY_TO_YOUR_PEM .
```
<b>Make sure you add the `.` at the end to copy to your current directory</b>

![image](https://user-images.githubusercontent.com/72572922/164916438-2b4960e1-883e-4c3d-a6a8-17bd80dfbb0e.png)

Next, we'll change the permission on the `.pem` file. Enter the following code block
```bash
chmod 400 YOUR_PEM_FILE.pem
```

![image](https://user-images.githubusercontent.com/72572922/164917047-188bce88-15df-4329-b3e1-df7159cc2de4.png)

In the `Connect to instance` window, copy the `SSH` command by clicking the copy button.

![image](https://user-images.githubusercontent.com/72572922/164916917-0d626a51-2d75-4e4b-bd20-1df1e2f02bfd.png)

Paste that command in terminal and confirm by type `yes` when prompted about connecting.

![image](https://user-images.githubusercontent.com/72572922/164919176-4488d88b-c723-4be6-a079-d439a4fcf475.png)

</details>





















### Setting up the EC2 Environment
<details>
     <summary><b>Click to Expand</b></summary>

<br>

Copy and paste the first line to update `yum` (your package manager). We'll also install `git` using the second command.
``` bash
sudo yum update -y
```
``` bash
sudo yum install git -y
```

![image](https://user-images.githubusercontent.com/72572922/164928584-89342d8d-aad2-4f8b-9f94-3927964f5ebb.png)

We'll then download `Anaconda`

```bash
wget https://repo.anaconda.com/archive/Anaconda3-2021.11-Linux-x86_64.sh
```
![image](https://user-images.githubusercontent.com/72572922/164933544-c289403c-f6d1-41d7-9aa8-5f71d9e32ec5.png)

![image](https://user-images.githubusercontent.com/72572922/164933698-55c13d3c-54c9-44a2-8237-1cbae6bd8e1b.png)

``` bash
bash Anaconda3-2021.11-Linux-x86_64.sh
```

![image](https://user-images.githubusercontent.com/72572922/164933715-4f2f9f6c-fb6a-4f89-828e-a00886f8ac1f.png)

![image](https://user-images.githubusercontent.com/72572922/164933727-0d3e0908-3e98-4b7a-b229-a05e2798f219.png)

You can hit <kbd>space</kbd> key a few times to jump through the documentation. Type `yes` to the prompt about accepting the license terms and hit <kbd>Enter</kbd>.

![image](https://user-images.githubusercontent.com/72572922/164933822-bd3c82ed-59a8-4271-bd3c-c53726fa6ca2.png)

Answer `yes` to the prompt about initializing `conda init` and press <kbd>Enter</kbd>

![image](https://user-images.githubusercontent.com/72572922/164933956-4ab7e4bf-c9ad-4720-a47c-716815196a76.png)

Copy the following code block to update your bashrc file and access `conda`

``` bash
source ~/.bashrc
```

![image](https://user-images.githubusercontent.com/72572922/164934017-b1770c9c-9a37-485a-9320-8dd0cb8548da.png)

Let's clone our repository from before in EC2 with its updates using the following

``` bash
git clone YOUR_REPO_LINK@GIT
```
![image](https://user-images.githubusercontent.com/72572922/164934244-fdec6d85-bf39-4da7-8acc-e60fb61d5f76.png)

`cd` into your git directory and run your `main.py`
![image](https://user-images.githubusercontent.com/72572922/164934368-c804f0ae-70c2-4ba7-8801-9cff1149ec1a.png)
![image](https://user-images.githubusercontent.com/72572922/164934404-adc26b53-cd95-44f1-bd02-f94e70584af5.png)

#### Great work! You've just run your code on AWS!
In the future we can continuously make updates from our local machine and push them to our EC2 instance, taking full advantage of the instance hardware!

</details>
