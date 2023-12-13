# JumpServer - ByPassing IP Restriction
JumpServer is the world's first open-source Bastion Host and is licensed under the GPLv3. It is a 4A-compliant professional operation and maintenance security audit system. JumpServer uses Python / Django for development, follows Web 2.0 specifications, and is equipped with an industry-leading Web Terminal solution that provides a beautiful user interface and great user experience 
This is a public available vulnerability for bypassing the restriction of IP Whitelisting function in JumpServer 

## Environment
Platform: Docker
Operation System: Ubuntu 22.04
Image Version: JumpServer Image 3.9.3
![image](https://github.com/N0th1n3/JumpServer-IPRestrictionBypass/assets/150101148/0a426b31-704f-49e9-a53d-12b5f75e5e34)

## Step to Reproduce
Step 1. Set up a Blacklist Rules of Priority 50 on rejecting all connection for the user **[Jeff]**
![image](https://github.com/N0th1n3/JumpServer-IPRestrictionBypass/assets/150101148/61348d1f-113f-4a00-9c16-d09b28a4766b)
<img width="711" alt="image" src="https://github.com/N0th1n3/JumpServer-IPRestrictionBypass/assets/150101148/41ebdf2a-68a9-4ca8-8fe8-f63e09d49770">


Step 2. Setup a whitelist rules of Priority 1 (in order to prioritize whitelist rule over blacklist rule) which whitelist the user **[Jeff]** with the IP Address "10.0.0.1" which does not exist in the network

<img width="512" alt="image" src="https://github.com/N0th1n3/JumpServer-IPRestrictionBypass/assets/150101148/5a62f2fa-17ff-4214-b342-8551512586e4">

## Expected Behaviour
With normal condition, the IP restriction should block the user from accessing the portal 
<img width="823" alt="image" src="https://github.com/N0th1n3/JumpServer-IPRestrictionBypass/assets/150101148/2cebda6c-ac9f-42bc-b3e0-442dc5597d95">
<img width="644" alt="image" src="https://github.com/N0th1n3/JumpServer-IPRestrictionBypass/assets/150101148/79d26720-8d22-4517-bc8e-a2f61204f009">

## Actual Behavour with Request Rewrite
We have supplemented the header of "X-Real-IP: 10.0.0.1" and the successfully logged into the JumpServer Portal
<img width="824" alt="image" src="https://github.com/N0th1n3/JumpServer-IPRestrictionBypass/assets/150101148/44b9af4c-2919-49af-a21f-336b76ea0759">
<img width="815" alt="image" src="https://github.com/N0th1n3/JumpServer-IPRestrictionBypass/assets/150101148/dee3f571-a6b2-45f3-8f6b-88bb31700699">

