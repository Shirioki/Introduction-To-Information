
## Karvinen 2021: Install Debian on Virtualbox - Updated 2024

- this article was about the introduction to installing Debian on Virtualbox
- Debian (64-bit)
- Memory Size: 4000 MB (more is better if you have enough RAM, 2000 MB could work)

## Karvinen 2020: Command Line Basics Revisited

- Basic command lines for linux
- Moving and looking around commands
- File manipulation commands
- SSH Remote control
- Administration commands and packages
- Help commands

  ## a) Cant fish

  - I opened terminal emulator and checked my ip address with ip addr command then i used sudo ifconfig enp0s3 up to disconnect my network after that i checked with ping 8.8.8.8 if packets went through.

<img width="1088" alt="Screenshot 2025-02-03 at 0 55 46" src="https://github.com/user-attachments/assets/9b3d3065-8e46-465b-852e-473031fb0780" />

## b) Local only

<img width="801" alt="Screenshot 2025-02-03 at 1 07 17" src="https://github.com/user-attachments/assets/8bba84f2-5da8-465e-8470-a94b932325d2" />

- mass_dns : warning... indicates that my computer is disconnected from the internet and there are no DNS servers available
- Scan is done with local machine and open ports are 25/tcp (SMTP = simple mail transfer protocol) and 631/tcp (ipp = Internet printing protocol)
- ''' Not shown: 998 closed tcp ports (conn-refused) '''
  indicates that 998 ports were closed.

## c) Daemon scan

<img width="1055" alt="Screenshot 2025-02-03 at 1 32 44" src="https://github.com/user-attachments/assets/18df335c-722c-4a5b-ba35-83e83601b9c3" />

- I noticed from daemon scan that we got one more tcp port 80/tcp open (http) port.

## d) Bandit oh-five

### Level 0
<img width="699" alt="Screenshot 2025-02-03 at 1 46 27" src="https://github.com/user-attachments/assets/26d87dbf-42bd-49ad-8946-79e505c08cee" />

### Level 1
<img width="840" alt="Screenshot 2025-02-03 at 1 51 25" src="https://github.com/user-attachments/assets/e5ac052f-7ee6-4012-b4d1-bbc52daeb349" />

### Level 2

<img width="335" alt="Screenshot 2025-02-03 at 1 55 37" src="https://github.com/user-attachments/assets/5a1471a0-b658-4de2-bbe0-3290c9c738e7" />

### Level 3

<img width="484" alt="Screenshot 2025-02-03 at 1 58 58" src="https://github.com/user-attachments/assets/5ad12980-fbde-43a2-b2c2-b5e448779bcf" />

### Level 4

<img width="503" alt="Screenshot 2025-02-03 at 2 03 17" src="https://github.com/user-attachments/assets/a006961e-7361-4f62-a05c-a27e7cf69334" />


