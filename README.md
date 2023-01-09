# **Linux Systems Administration**


### *Step 1: Ensure/Double Check Permissions on Sensitive Files*


### 1. Permissions on /etc/shadow should allow only root read and write access.


  - #### a. **Command to inspect permissions**:


         ls -l /etc/shadow
	

   - #### b. **Command to set permissions (if needed)**:


         Sudo chmod 600 /etc/shadow
	

### 2. Permissions on /etc/gshadow should allow only root read and write access.


   - #### a. **Command to inspect permissions**:


           ls -l /etc/gshadow
	

   - #### b. **Command to set permissions (if needed)**:


           Sudo chmod 600 /etc/gshadow
	


### 3. Permissions on /etc/group should allow root read and write access, and allow everyone else read access only.


   - #### a. **Command to inspect permissions**:


         ls -l /etc/group
	

   - #### b. **Command to set permissions (if needed)**:


          Sudo chmod -644 /etc/group
	

### 4. Permissions on /etc/passwd should allow root read and write access, and allow everyone else read access only.


   - #### a. **Command to inspect permissions**:


         ls -l /etc/passwd
	

   - #### b. **Command to set permissions (if needed)**:


         Sudo chmod 644 /etc/passwd
	

## *Step 2: Create User Accounts*


### 1. Add user accounts for sam, joe, amy, sara, and admin with the useradd command.


   a. **Command to add each user account (include all five users)**:


    sudo useradd sam
    sudo useradd joe
    sudo useradd amy
    sudo useradd sara
    sudo useradd admin
	

### 2. Ensure that only the admin has general sudo access.


   - #### a. **Command to add admin to the sudo group**:


         Sudo usermod -a -G sudo admin
	

### Step 3: Create User Group and Collaborative Folder


   - ### 1. **Add an engineers group to the system**.


        + #### 1. **Command to add group**:


         Sudo groupadd engineers
	

### 2. Add users sam, joe, amy, and sara to the managed group.


   - #### 2. Command to add users to engineers group (include all four users):


    sudo usermod -a -G engineers sam
    sudo usermod -a -G engineers amy 
    sudo usermod -a -G engineers joe
    sudo usermod -a -G engineers sara
	

### 3. Create a shared folder for this group at /home/engineers.


   - #### 3. **Command to create the shared folder**:


         sudo mkdir -p /home/engineers
	

### 4. Change ownership on the new engineers’ shared folder to the engineers group.


   - #### 4. **Command to change ownership of engineers’ shared folder to engineers group**:


         Sudo chmod -R 775 /home/engineers 
	

## *Step 4: Lynis Auditing*


 ### 1. Command to install Lynis:


    sudo apt-get install lynis -y
	

### 2. Command to view documentation and instructions:


    Sudo lynis -h
	

### 3. Command to run an audit:


    sudo lynis audit system
	
