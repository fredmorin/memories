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
    sudo mount //192.168.0.154/home mnt/nas -t cifs -o user=admin,uid=$(id -u),gid=$(id -g),forceuid,forcegid
    ```
6. Setup elodie https://github.com/jmathai/elodie

    ```
    sudo apt-get install python-pip
    sudo apt-get install git
    apt-get install libimage-exiftool-perl
    git clone https://github.com/jmathai/elodie.git
    cd elodie
    pip install -r requirements.txt
    mkdir ~/.elodie
    cp config.ini-sample ~/.elodie/config.ini
    ```
7.  Elodie requires a mapquest api key in order to geocode photos and videos. Register to mapquest and insert your api key in ~/.elodie/config.ini https://developer.mapquest.com/plan_purchase/steps/business_edition/business_edition_free/register

# Import medias
1. Create folders
    ``` 
    mkdir ~/mnt/nas/memories
    mkdir ~/mnt/nas/imported    
    ```
2. Import existing medias in memories and move old files to imported. (or to trash)
    ```
    ./elodie/elodie.py import --source ~/mnt/nas/Londres ~/mnt/nas/memories
    mv ~/mnt/nas/Londre ~/mnt/nas/imported
    ```





