# memories
Personal photos and videos automation.


# Setup Raspberry PI
1. Download and write raspbian image to sd-card https://www.raspberrypi.org/documentation/installation/installing-images/
2. Login (pi/raspberry)
3. Change password 

    ```
    passwd
    ```    
4. Enable SSH https://www.raspberrypi.org/documentation/remote-access/ssh/ 

    ```
    sudo systemctl enable ssh
    sudo systemctl start ssh
    ```
5. Mount NAS
    ```
    sudo mount //192.168.0.154/Download mnt/nas -t cifs -o user=admin,uid=$(id -u),gid=$(id -g),forceuid,forcegid
    ```
6. Setup elodie https://github.com/jmathai/elodie

    ```
    sudo apt-get install python-pip
    sudo apt-get install git
    apt-get install libimage-exiftool-perl
    git clone https://github.com/jmathai/elodie.git
    cd elodie
    pip install -r requirements.txt
    ```
7. 


