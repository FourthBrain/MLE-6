# Connecting To AWS & GCP VM's in VS Code

## VS Code & SSH Config
1. Install the "Remote-SSH" extension.
2. Go to your `.ssh/config` file and add your VM details when ready including your identity file.

## AWS
1. Create VM with public ip.
2. Make sure the VM has port 22 open so you can ssh into it.
3. Download your `.pem` file if you don't have it already.
4. In VS Code, use the "Remote-SSH" extension in the bottom left to "Connect to Host" and choose the Host you created above in your `.ssh/config` file associated with the VM you created.

Some considerations:
* Make sure your security group allows traffic on SSH port 22
* Make sure you are using a public subnet
* I chose the Ubuntu Server 20.04 AMI
* When connected, if you chose the same AMI, you will need to install pip which means you'll need to run:
```
sudo apt update
sudo apt install python3-pip
```

## GCP
You can follow these [instructions](https://cloud.google.com/compute/docs/instances/connecting-advanced#thirdpartytools) too.

Looks like you need to manually generate an SSH key for your instance and then provide it to GCP during VM creation under "Security" and then "VM Access". To create your own SSH key do the following:

* `ssh-keygen -t rsa -f {KEY_FILENAME} -C {USER} -b 2048`

Where `KEY_FILENAME` is the name of your SSH key file and `USER` is your username. Since I am using Ubuntu Server 20.04, I'll just keep my `USER` as `ubuntu`. 

1. Enter the `.pub` key to the "Add manually generated SSH keys" field.
2. In VS Code, use the "Remote-SSH" extension in the bottom left to "Connect to Host" and choose the Host you created above in your `.ssh/config` file associated with the VM you created.

## Once Connected To Instance
* You'll need to run:
```
sudo apt update
sudo apt install python3-pip
```
This will get Python and pip set up for you.

* Make a new directory called code, then make your `hello_world.ipynb` notebook. From here you will be prompted to select a kernel.

* Go with the default kernel which should prompt you to install kernel from the marketplace which will get you Jupyter.

* From there go back to your notebook and select your Python 3 kernel. This will require you to download the Python extension.

* Lastly, try running the cell and it will prompt you to install ipykernel which makes it so you can run interactive cells in the notebook.

* Now you should be good to go to run the code!