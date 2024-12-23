<h1 align="center">Installing Sonaric AI Node</h1>
In this tutorial, we install Sonaric AI Node on a Linux machine to receive points

> Node requirements are very low, You can run this alongside your other nodes

## System Requirements
| Ram | cpu     | disk                      |
| :-------- | :------- | :-------------------------------- |
| `2 GB`      | `2 Core` | `10-20 GB SSD` |

## 1. Dependecies
```console
# Update packages
sudo apt update && apt upgrade -y

sudo apt install curl make wget clang net-tools pkg-config libssl-dev build-essential jq lz4 gcc unzip snapd -y
```

## 2. Sonaric Node
```console
sh -c "$(curl -fsSL https://get.sonaric.xyz/scripts/install.sh)"
```
* After Installation, Your node starts running in the background

## 3. Check your node is running
```console
sonaric node-info
```
![Screenshot_143](https://github.com/user-attachments/assets/d0bd314b-2d65-49cd-8057-e7ae1a84bf5a)

## 4. Update Sonaric
```console
apt-get update
apt-get install sonaricd sonaric

# To confirm the node is running the latest version
sonaric node-info

# Update if needed
sh -c "$(curl -fsSL https://raw.githubusercontent.com/monk-io/sonaric-install/main/linux-install-sonaric.sh)"
```

## 5. Optional: Access GUI Dashboard (Check Rank & Points)
* This step is optional, Do this only if you want to access the Sonaric GUI dashboard running on your VPS to check your points and node status

 1- You need to run the following command in your local machine like your Windows and **NOT in your VPS**
 
 2- You need to install WSL ubuntu (Linux terminal) on your Windows -- [How To Intall WSL Ubuntu on Windows](https://github.com/0xmoei/Install-Linux-on-Windows)

 3- Before run the command, Replace `user` with your VPS username (usually it's `root`) and `your-vps-ip` with your VPS IP address

 4- After entering the command, You must Enter Yes, and your VPS password
```console
ssh -L 127.0.0.1:44003:127.0.0.1:44003 -L 127.0.0.1:44004:127.0.0.1:44004 -L 127.0.0.1:44005:127.0.0.1:44005 -L 127.0.0.1:44006:127.0.0.1:44006 user@your-vps-ip
```
 5- Open a web browser on your local machine and navigate to http://localhost:44004 to access the Sonaric GUI.

![Screenshot_144](https://github.com/user-attachments/assets/fd6e028a-a6a6-48f6-a415-e15a8654bfc0)

#

You can check your points by entering this command in VPS `sonaric points`

![image](https://github.com/user-attachments/assets/068eb151-6f1f-43a4-aa7e-930713fcb1de)

#

## 6. Backup your node

* In order to export the current identity of your node to a file called your-node-name.identity, run the following command
```console
sonaric identity-export -o your-node-name.identity
```
> You can specify a different file name by changing your-node-name.identity to the desired file name. The name is arbitrary and can be anything you like.
>
> Transfer and save the file in your local PC. You can use Mobaxterm or Termius to directly access to your directories
>
> It is normal to see different file contents each time you export the identity. The file is encrypted using a method that randomizes the output.

## 7. Receive 100 Points
To receive instant **100** points, you can use this referral code in GUI dashboard: `nwfq5ty`

![Screenshot_146](https://github.com/user-attachments/assets/ed49be70-d765-49dd-81b2-b097aef2354f)

## 8. Discord Role (Operator)

Join Discord: https://discord.gg/jy5EZwhtZH

**1- Type: /addnode in #general**

**2- Copy the code**

![image](https://github.com/user-attachments/assets/1c83be62-27c1-418a-8c61-c377a8feeb73)

**3- Move to your VPS, then replace your code with `CODE`:**
```
sonaric node-register CODE
```

![image](https://github.com/user-attachments/assets/017acf1b-1aaf-44f1-8ac8-31382c72311e)

**Type: /node in #general to list your nodes**

## 9. Multiple Nodes
**You can add multiple nodes to your cluster by just adding them to your discord account in the same way**

### 10. Optional: Delete node
```
sudo apt remove --purge sonaricd sonaric
```
