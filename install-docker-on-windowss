# Instalasi Docker Desktop di Windows:

## 1. Update Windows 10 ke v.22H2
- Donwload [Windows Update Assistance](https://www.microsoft.com/en-us/software-download/windows10) 
- run `Windows10Upgrade9252.exe`
- restart PC

## 2. Update WSL2 windows 10 22H2

1. Update wsl to wsl2 run:
    ```
    wsl.exe --update
    ```

2. Ensure the distribution runs in WSL 2 mode. WSL can run distributions in both v1 or v2 mode.
To check the WSL mode, run:
    ```
    wsl.exe -l -v
    ```
3. To upgrade the Linux distro to v2, run:
    ```
    wsl.exe --set-version <distro name> 2
    ```
4. To set v2 as the default version for future installations, run:
    ```
    wsl.exe --set-default-version 2
    ```

    When Docker Desktop starts, go to Settings > Resources > WSL Integration.

5. The Docker-WSL integration is enabled on the default WSL distribution, which is Ubuntu. To change your default WSL distro, run:
    ```
    wsl --set-default <distro name>
    ```
    
6. Select Apply & Restart.

