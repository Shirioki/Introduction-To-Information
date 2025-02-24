
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

## Automate SSH connection using public keys

To generate a key pair i used command 

```
ssh-keygen
```

after creating public key i copied it to the server using 

```
ssh-copy-id ponkiphan@127.0.0.1
```

Now when i logged into my own server it will be passwordless

```
ssh ponkiphan@127.0.0.1
```
