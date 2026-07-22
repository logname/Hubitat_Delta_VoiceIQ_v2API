# Hubitat Delta Faucet VoiceIQ v2
**Hubitat Driver Code for Delta Faucet VoiceIQ v2 API**

This driver was built using OpenAI based on the script found here:
https://gist.github.com/velaar/4e18a200c1db7b06109a3fd840838684

Thanks to all from the Hubitat community that participated in its creation!  More information here:
https://community.hubitat.com/t/integration-to-delta-voiceiq/119842?u=sebastien

**Setup**:

**The required token will expire after approximately 6 months, at which time you will need to repeat step 2-9 and step 12 below to retrieve a new authorization token. You do not need to reset your faucet when the authorization token expires, you simply retrieve the new token and save it to the Delta Faucet driver on Hubitat.**

1. Reset your VoiceIQ module and set it up again using the DFC@Home app
   
**NOTE**: I had trouble getting my Gen 1 module to connect at first. The DFC@Home app showed that it joined my 2.4 GHz WiFi, but the green light was not solid on the module. I unplugged the RJ-45 connection from the module for just 1 second (too long and it will reset again). This worked and the LED turned solid green.

2. Using Google Chrome, navigate to [https://device.deltafaucet.com/#/](https://device.deltafaucet.com/#/)
3. Select the Gen2 VoiceIQ link (even if you have a Gen 1 VoiceIQ module)
4. Check the box at the bottom of the page first

**By signing in, I have read and agreed to Delta Faucet's Privacy Policy**

5. Login with whatever method you used in the app. It shouldn’t matter if you use Amazon, Apple or Google
   
   **NOTE**: If one sign-in method cannot control the faucet, you can use another. For example, you login via Amazon but the faucet usage amount shows zero gallons and the faucet cannot be controlled. You should be able to resolve the issue by signing out of your Delta faucet account and sign-in again using a different sign-in method such as Apple or Google. You will still be able to retrieve the required information using the following steps.
   
6. From the Chrome **View** menu at the top of the screen, select **Developer** > **JavaScript Console**
7. At the top of the console window, click on the **Network** tab
8. On the Delta faucet page, click on the blue button labelled **Water Usage - This Week**
9. Expand the left side of the inspector window
10. On the **Name** column, click on the result that starts with **UsageReport?macAddress=**
11. Copy the MAC Address, since you will need later to enter on the **Preferences** tab of the Hubitat driver
   
    **Do not include : or spaces in MAC Address**
    
12. On the **Headers** tab, under **Request Headers** you will find the required the full **Authorization** token needed.

   **NOTE**: Copy the entire Authorization token _after_ the word **Bearer**

<img width="1279" height="618" alt="Screenshot 2025-12-26 at 1 48 27 PM" src="https://github.com/user-attachments/assets/464347e6-ed62-414f-b76a-4c299eda24fc" />

