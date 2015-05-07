# Run headless chrome in linux

### Cent OS

1. Install Chrome 

    Add following to /etc/yum.repos.d/google.repo file:
    
    32-bit
    ```
    [google]
    name=Google - i386
    baseurl=http://dl.google.com/linux/rpm/stable/i386
    enabled=1
    gpgcheck=1
    gpgkey=https://dl-ssl.google.com/linux/linux_signing_key.pub
    ```
    64-bit
    ```
    [google64]
    name=Google - x86_64
    baseurl=http://dl.google.com/linux/rpm/stable/x86_64
    enabled=1
    gpgcheck=1
    gpgkey=https://dl-ssl.google.com/linux/linux_signing_key.pub
    ```
    
    and then run 
    
    ```
    # yum install google-chrome-stable
    ```
    
2. Install XVBF
  
    ```  
    # yum info xorg-x11-server-Xvfb
    ```

3. set DISPLAY enviroment variable
    
    ```
    # export DISPLAY=:99
    ```
4. run XCFB server

  ```
  # /usr/bin/Xvfb :99 -screen 0 1280x1024x24 &
  ```

5. run chrome 
  
  ```
  # google-chrome --no-sandbox
  ```
