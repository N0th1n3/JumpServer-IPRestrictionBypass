# JumpServer - ByPassing IP Restriction
JumpServer is the world's first open-source Bastion Host and is licensed under the GPLv3. It is a 4A-compliant professional operation and maintenance security audit system. JumpServer uses Python / Django for development, follows Web 2.0 specifications, and is equipped with an industry-leading Web Terminal solution that provides a beautiful user interface and great user experience 
This is a public available vulnerability for bypassing the restriction of IP Whitelisting function in JumpServer 

## Environment
Platform: Docker
Operation System: Ubuntu 22.04
Image Version: JumpServer Image 3.9.3
![image](https://github.com/N0th1n3/JumpServer-IPRestrictionBypass/assets/150101148/0a426b31-704f-49e9-a53d-12b5f75e5e34)

## Step to Reproduce
Step 1. Set up a Blacklist Rules on rejecting all connection for the user **[Jeff]**
![image](https://github.com/N0th1n3/JumpServer-IPRestrictionBypass/assets/150101148/0b296c15-39c7-4f01-8936-872e4cb3d984)

Step 2. Setup a whitelist rules which whitelist the user **[Jeff]** with the IP Address "10.0.0.1" which does not exist in the network
![image](https://github.com/N0th1n3/JumpServer-IPRestrictionBypass/assets/150101148/29b3633c-881d-478c-aa41-cdbce05ed213)

## Normal Behaviour
With normal condition, the IP restriction should block the user from accessing the portal 
![image](https://github.com/N0th1n3/JumpServer-IPRestrictionBypass/assets/150101148/21637f9b-2a6b-45f9-8de4-3e070ca9fee3)
![image](https://github.com/N0th1n3/JumpServer-IPRestrictionBypass/assets/150101148/c718b504-2bab-419b-9cfc-4e149e89f23a)


## Actual Behavour with Request Rewrite
We have supplemented the header of "X-Real-IP: 10.0.0.1" and the successfully logged into the JumpServer Portal
![image](https://github.com/N0th1n3/JumpServer-IPRestrictionBypass/assets/150101148/114ab176-0ebe-413d-9503-5f780c68b1a3)
![image](https://github.com/N0th1n3/JumpServer-IPRestrictionBypass/assets/150101148/904bbc9e-aac0-4bd2-a2ae-70cffbcb4486)
