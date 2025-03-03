# € Schneier 2015: Applied Cryptography:

### One-way functions
- One-way functions are simple to compute, but difficult to reverse
- Not useful on encryption, cause you cant decrypt it.
- Trapdoor one-way function
### One-way hash functions
- Hash-function = takes a variable-length input string (called a pre-image) and converts it to a fixed-length (generally smaller) output string (called a hash value).
- Hash-function are many-to-one
- Good one-way hash-functions are collision free. Meaning that two pre-images cannot be determined with the same hash value.
  
## a) Install Hashcat

I installed hashcat using teros introductions and using command 

<img width="803" alt="image" src="https://github.com/user-attachments/assets/ce6e7bbf-f02a-4018-94f1-dbe731631a08" />

After successfully installing hashcat i created a new dictionary and downloaded Rockyou big dictionary.

<img width="804" alt="image" src="https://github.com/user-attachments/assets/eb741025-a35d-4300-ac61-252e8a2a50f1" />

<img width="674" alt="image" src="https://github.com/user-attachments/assets/5702bf6b-fbef-4bcb-8b46-e21e31cf78d4" />

After this i had to identify the hash type with command

<img width="835" alt="image" src="https://github.com/user-attachments/assets/6c843184-b47f-422a-a423-38dfc8aa72a7" />

then we had to tried to crack the hash with md5 

<img width="878" alt="image" src="https://github.com/user-attachments/assets/2f1aa48d-f691-4568-aa24-3ee1fb81a92c" />


Successfully cracked the sample hash 

<img width="514" alt="image" src="https://github.com/user-attachments/assets/fe844538-a485-4507-85ee-01cbdd60e5a6" />

## b) Crack this hash: d595b2086532422bbe654bc07ea030df

I did exactly the same as in the previous exercise.

<img width="531" alt="image" src="https://github.com/user-attachments/assets/1f70709f-1fe9-4710-a361-299004e4f9dd" />

## References

Schneier 2015: Applied Cryptography: https://www.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec003

Karvinen 2022: Cracking Passwords with Hashcat: https://terokarvinen.com/2022/cracking-passwords-with-hashcat/
