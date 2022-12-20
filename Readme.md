# NachOS (2022.12.20)

## Environment

- HW: Macbook pro 16 (2019) i7-9750H with macOS 12.4

- Virtual Machine
  - Virtual BOX 7.0.4
    - Free
    - Incredibly slow (Even though I've set the resolution to low.)
    - It doesn't work properly after installing Virtual BOX Tools.
  - VMWare Fusion Player 13.0.0
    - Free (For personal use)
    - Much faster (That's what I'm using now.)
    - I successfully install VMWare Tools but the Shared Folder isn't available.
  - Parallels Desktop 18.1.1
    - Paid
    - Much faster
    - I can't successfully install PD Tools on Ubuntu 14.04. (It got stuck while reboot after installing the Tools.)
    
- Virtual OS: 14.04.0 LTS (32 bits) ( ≤ 14.04.0)

## Set up 

- Get Ubuntu 14.04.0 LTS (32 bits)
- Prepare te NachOS 4.0 Package and the cross compiler as well
  - [Folder] nachos-4.0 or [File] nachos-4.0.tar.gz 
    (Put the folder in /home/<username>)
 
  - [Folder] mips-x86.linux-xgcc or [File] mips-x86.linux-xgcc.tar.gz
    (Put the folder in / )
    (Maybe you need: ```sudo tar -zxvf /mips-x86.linux-xgcc.tar.gz```)
    (Maybe you need: ```sudo mv mips-x86.linux-xgcc / ```)
  
- Set up the dependency
  - ```sudo apt-get install csh```
  - ```sudo apt-get install g++```
  - ```sudo cp -r /home/<username>/nachos-4.0/usr/local/ /usr```
  (If it works, you'll see the nachos folder in /usr/local )
  
- Compile the NachOS
  - ```cd /home/<username>/nachos-4.0/code```
  - ```make clean```
  - ```make ```

- Test NachOS
  - ```cd userprog```
  - ```./nachos –e ../test/test1```
