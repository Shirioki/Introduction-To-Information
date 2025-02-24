
# h5 Uryyb, Greb!

## € Schneier 2015: Applied Cryptography: Chapter 1: Foundations

- Disguising a message to hide its substance is called encryption. This encrypted message is ciphertext
- Keeping messages secure is cryptography.
- Cryptographers specialize in making secure encryptions and cryptanalysts focus on breaking these messages.

## Installing OpenSSH server

- I started by opening terminal and used command 
  
```
 sudo apt-get install openssh-server
```

  to install OpenSSH server. Then I logged in to my own server using the command 

```
ssh 127.0.0.1
```

<img width="802" alt="Screenshot 2025-02-24 at 3 53 05" src="https://github.com/user-attachments/assets/0baf565e-75cf-42db-8276-ba242780dc31" />


## Automate SSH connection using public keys

To generate a key pair i used command 

```
ssh-keygen
```
<img width="804" alt="image" src="https://github.com/user-attachments/assets/6928cd48-a6c4-42a2-9d06-7a522a4d9519" />

after creating public key i copied it to the server using 

```
ssh-copy-id ponkiphan@127.0.0.1
```
<img width="897" alt="image" src="https://github.com/user-attachments/assets/0f6e479c-6aa4-48ac-b816-dd3d7f80cb58" />

Now when i logged into my own server it will be passwordless

```
ssh ponkiphan@127.0.0.1
```

## Pretty Good indeed

<img width="803" alt="Screenshot 2025-02-24 at 4 35 39" src="https://github.com/user-attachments/assets/4eddfe60-9ca4-49e3-8dbb-650c3d911e34" />

## Password manager, open and cloudless

- Protects you from phishing, keyloggers and weak passwords
- saves strong and unique passwords

### KeePassxC

- Open-sourced, doesnt rely on cloud services.

To install it 

```
sudo apt install keepassxc
```
  
