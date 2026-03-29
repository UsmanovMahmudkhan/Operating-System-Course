# This is a guide to have passwordless SSH Communication using the public and private key concept.

## STEP-1 Create Key Pair
Create a public and private key pair in your source machine [From where you want to access the remote PC (Target) ]
- Type the following command; it is the same in Linux and Windows both. This will create a private and public SSH key with a hash code RSA 3070 something 
```
ssh-keygen
```

## STEP-2 Copy Public Key to the target machine for communication
  2. We need to copy its public key to the target PC location. There are two ways.
  #### Method-1
  - Go to the source PC location `/home/.shh/<.public>`. Copy this key and past at the in the target PC.
  - 
![image](https://github.com/user-attachments/assets/9e7fdc46-8c4c-4f07-89f8-89a7e0a6e7f9)

  - `/home/.ssh/authorized_keyys `. If there is no file, you can create one
    
![image](https://github.com/user-attachments/assets/4f4284c1-a287-47d7-a520-af803d82ece9)
    
 #### Method-2
  - From the source PC, just run the command below. It will automatically copy the key to the target. This command works for both Windows and Linux
    
  ```
  ssh-copy-id <remote PC user>@<REmote PC IP>
  ```

 Example 
```
ssh-copy-id zubair@100.100.100.100
```
![image](https://github.com/user-attachments/assets/7c8a352b-78ef-4179-be00-7c20b60285fe)


> [!IMPORTANT]
> SSH passwordless communication is based on the user.

# 
- SSH depends on the user, which user we want to SSH, and does mapping
- Example: I am on `zubair1.`

### Create a New user and give Access as Root 
- add user in Ubuntu
```
useradd <user Name>
```
