# Setup Overview

This section provides an overview of the **offline Linux server setup process**. The server environment is being configured **without direct internet access**, which means all required software, dependencies, and installation packages must be prepared in advance on a separate machine that has internet connectivity.

The setup process begins by downloading the Linux versions of all required software and supporting files on an internet-enabled PC. These files are then securely transferred to the target Linux server using tools such as **WinSCP**, **1Remote**, and **PuTTY** for file transfer, remote access, and command-line configuration.

Because the setup is performed in an offline environment, special attention is given to dependency management, package completeness, and step-by-step installation sequencing to ensure a smooth and reliable deployment. This approach helps maintain controlled environments, improves security, and supports systems operating in restricted network conditions.

This are the followings steps we will follow to setup our linux server 

[Installation of Python ](Setup%20Overview/Installation%20of%20Python%2030a2dc291ad68090b4c5c46add2a03b4.md)

[Installation of Docker ](Setup%20Overview/Installation%20of%20Docker%2030a2dc291ad6806692f4c2e3a67f4277.md)

[Initialize Third Party Services ](Setup%20Overview/Initialize%20Third%20Party%20Services%2030a2dc291ad68000b837f324681a1be2.md)

[My Sql Initialization ](Setup%20Overview/My%20Sql%20Initialization%2030a2dc291ad680409f2deb2100261677.md)