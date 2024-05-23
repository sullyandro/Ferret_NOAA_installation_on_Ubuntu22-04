**Ferret NOAA installation on Ubuntu 22.04**


**1\. Download the Ferret datasets package**

<https://github.com/NOAA-PMEL/FerretDatasets/releases>

You should click on “**Source code**” to download the **FerretDatasets-7.6.tar.gz**

<img src="https://github.com/sullyandro/Ferret_NOAA_installation_on_Ubuntu22-04/blob/main/figure1.png" height="300">


**2\. Download the Ferret executables scripts package**

<https://github.com/NOAA-PMEL/Ferret/releases>

![](https://github.com/sullyandro/Ferret_NOAA_installation_on_Ubuntu22-04/blob/main/figure2.png)

**3\. Installation**

**Note:** “**$user**” referred to in this document should be replaced with your username.

**Choose a directory for the installation:**

$ mkdir /home/**$user**/apps/ferret

**Extract both ferret packages downloaded to the following paths:**

Ferret-7.6.0-RHEL7.tar.gz **->** /home/**$user**/apps/ferret/Ferret-7.6.0-RHEL7/

FerretDatasets-7.6.tar.gz **->** /home/**$user**/apps/ferret/FerretDatasets-7.6/

$ tar xf Ferret-7.6.0-RHEL7.tar.gz -C /home/**$user**/apps/ferret/

$ tar xf FerretDatasets-7.6.tar.gz -C /home/**$user**/apps/ferret/

![](https://github.com/sullyandro/Ferret_NOAA_installation_on_Ubuntu22-04/blob/main/figure3.png)

**Open a terminal and go to** /home/**$user**/apps/ferret/Ferret-7.6.0-RHEL7/bin/

$ cd /home/**$user**/apps/ferret/Ferret-7.6.0-RHEL7/bin/

**Execute the Finstall script:**

$ bash Finstall

- **(1, 2, 3, q, x) -->** 2
- **FER_DIR -->** /home/**$user**/apps/ferret/Ferret-7.6.0-RHEL7
- FER_DSETS --> /home/**$user**/apps/ferret/FerretDatasets-7.6
- desired ferret_paths location --> /home/**$user**/apps/ferret
- ferret_paths link to create? (c/s/n) \[n\] --> s
- (1, 2, 3, q, x) --> q

![](https://github.com/sullyandro/Ferret_NOAA_installation_on_Ubuntu22-04/blob/main/figure4.png)

**Open your** /home/**$user**/.bashrc **and write the following in the end:**

\# ferret

source /home/**$user**/apps/ferret/ferret_paths

**Open a new terminal and ferret should be available.**

![](https://github.com/sullyandro/Ferret_NOAA_installation_on_Ubuntu22-04/blob/main/figure5.png)

**You can find some missing system libraries when running ferret for the first time:**

$ ferret

ferret: error while loading shared libraries: **libreadline.so.6**: cannot open shared object file: No such file or directory

ferret: error while loading shared libraries: **libhistory.so.6**: cannot open shared object file: No such file or directory

**To solve it:**

$ sudo apt-get install libreadline-dev

$ sudo ln -s /lib/x86_64-linux-gnu/**libreadline.so.8** /lib/x86_64-linux-gnu/**libreadline.so.6**

$ sudo ln -s /lib/x86_64-linux-gnu/**libhistory.so.8** /lib/x86_64-linux-gnu/**libhistory.so.6**


**References:**

https://ferret.pmel.noaa.gov/Ferret/downloads/ferret-installation-and-update-guide

