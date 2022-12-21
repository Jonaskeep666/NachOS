# How to install NachOS (2022.12.20)

- HW: Macbook pro 16 (2019) i7-9750H with macOS 12.4

---

## [A] NachOS-4.0 (32bits ver)
- Original version for 32bits Linux
- Source: Farn's OS class, Nation Taiwan University

### A.1 Environment

- Virtual OS: 14.04.0 LTS (32 bits) (I don't update anymore...)

- Virtual Machine
  - Virtual BOX 7.0.4
    - Free
    - Incredibly slow (Even though I've set the resolution to low.)
    - It doesn't work properly after installing Virtual BOX Tools.
  - VMWare Fusion Player 13.0.0
    - Free (For personal use)
    - Much faster (That's why I'm using it now.)
    - I successfully install VMWare Tools but the Shared Folder isn't available.
  - Parallels Desktop 18.1.1
    - Paid
    - Much faster
    - I can't successfully install PD Tools on Ubuntu 14.04. (It got stuck while reboot after installing the Tools.)

### A.2 Build NachOS

- Prepare the NachOS 4.0 Package and the cross compiler as well
  - [File] nachos-4.0.tar.gz 
    - Unzip it.
    - Put the folder in /home/<username>
 
  - [File] mips-x86.linux-xgcc.tar.gz
    - Unzip it
      (Maybe you need: ```sudo tar -zxvf /mips-x86.linux-xgcc.tar.gz```)
    - Put the folder in /
      (Maybe you need: ```sudo mv mips-x86.linux-xgcc / ```)
  
- Set up the dependency
  - ```sudo apt-get install csh```
  - ```sudo apt-get install g++```
  - ```sudo cp -r /home/<username>/nachos-4.0/usr/local/ /usr```
  (If it works, you'll see the nachos folder in /usr/local )
  
- Compile the NachOS kernel
  - ```cd /home/<username>/nachos-4.0/code```
  - ```make clean```
  - ```make ```

- Test NachOS
  - ```cd userprog```
  - ```./nachos –e ../test/test1```
  
### A.3 Build & Run Test Programs

- Compile the test program (ex. halt.c)
  - ```cd /home/<username>/nachos-4.0/code/test```
  - ```make halt```
 
- Test NachOS
  - ```cd userprog```
  - ```./nachos –e ../test/test1```

---

## [B] NachOS-4.0 (64bits ver)
- Modified version for 64bits Linux
- Source: shawn2000100/10810CS_342301_OperatingSystem & Jerry's OS class, National Tsing Hua University


### B.1 Environment

- Virtual OS: Red Hat Enterprise Linux 9 (RHEL 9 x86_64)

- Virtual Machine
  - Parallels Desktop 18.1.1
    - I successfully install PD Tools but the "Drag & Drop" does't work.
    - I just use Share Folder instead.

### B.2 Build NachOS

- Prepare the NachOS 4.0 Package with the cross compiler as well
  - [File] NachOS-4.0_MP1.tar.gz
    - Unzip it.
    - Put the folder in /home/<username>
  
- Set up the dependency
  - ```sudo yum install gcc```
  - ```sudo yum install g++```
  - ```sudo yum install libstdc++.i686```
  
  - ```sudo cp -r /home/<username>/nachos-4.0/usr/local/ /usr```
  (If it works, you'll see the nachos folder in /usr/local )
  
  - ```sudo chmod -R 777 /home/vbox/NachOS-4.0_MP1/usr/local```
  - ```sudo chmod -R 777 /home/vbox/NachOS-4.0_MP1/coff2noff```
  - ```sudo chmod -R 777 /usr/local/nachos```
  
- Compile the NachOS kernel
  - ```cd /home/<username>/NachOS-4.0_MP1/code/build.linux```
  - ```make clean```
  - ```make depend``` <- It's important!
  - ```make```

- Test NachOS
  - ```./nachos –u```
  - ```./nachos –e ../test/halt```
  
### B.3 Build & Run Test Programs

- Compile the test program (ex. halt.c)
  - ```cd /home/<username>/NachOS-4.0_MP1/code/test```
  - ```make clean```
  - ```make halt```
 
- Test NachOS
  - ```/home/vbox/NachOS-4.0_MP1/code/build.linux/nachos -e ../test/halt```

---

## [C] Some errors
- If the Terminal shows something wrong about list.cc
  - Revising sth like : isEmpty() to this->isEmpty
- If /usr/bin/ld: cannot find libstdc++
  - ```sudo yum install libstdc++.i686```
- If it shows "... -I- ... -iquote instead" 
  - It doesn't matter
- make: ../../usr/local/nachos/bin/decstation-ultrix-gcc: ...
  - ```sudo chmod -R 777 /home/vbox/NachOS-4.0_MP1/usr/local```
- decstation-ultrix-gcc: installation problem, cannot exec `cc1': ?????????
  - ```sudo chmod -R 777 /home/vbox/NachOS-4.0_MP1/coff2noff```
- make: ../../coff2noff/coff2noff.x86Linux:...
  - ```sudo chmod -R 777 /usr/local/nachos```

---

## [D] Ref
- shawn2000100/10810CS_342301_OperatingSystem & Jerry's OS class, National Tsing Hua University
- Farn's OS class, Nation Taiwan University

- I'm so grateful for their dedication! It means a lot for autodidacts.
