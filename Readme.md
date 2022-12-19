# NachOS

## Set up

- Get Ubuntu 14.04.0 LTS
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
  - ```sudo cp -r /home/<username>/nachos-4.0/usr/local/ /usr/local```
  (If it works, you'll see the nachos folder in /usr/local )
  
- Compile the NachOS
  - ```cd /home/<username>/nachos-4.0/code```
  - ```sudo make clean```
  - ```sudo make ```
