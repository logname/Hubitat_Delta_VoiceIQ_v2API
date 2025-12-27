# Hubitat_Delta_Faucet
Hubitat Driver Code for Delta Faucet

This driver was built using OpenAI based on the script found here:
https://gist.github.com/velaar/4e18a200c1db7b06109a3fd840838684

Thanks to all from the Hubitat community that participated in its creation!  More information here:
https://community.hubitat.com/t/integration-to-delta-voiceiq/119842?u=sebastien

**Setup:**

1. Reset your VoiceIQ module and set it up again using the DFC@Home app
   
**NOTE**: I had trouble getting my Gen 1 module to connect at first. The DFC@Home app showed that it joined my 2.4 GHz WiFi, but the green light was not solid on the module. I unplugged the RJ-45 connection from the module for just 1 second (too long and it will reset again). This worked it the LED turned solid green.

2. Using Google Chrome, navigate to [https://device.deltafaucet.com/#/](https://device.deltafaucet.com/#/)
3. Select the **Gen2 VoiceIQ** link (even if you have a Gen 1 VoiceIQ module)
3. Check the box at the bottom of the page first
   
"**By signing in, I have read and agreed to Delta Faucet's Privacy Policy**"

4. Login with whatever method you used in the app. It shouldn’t matter if you use Amazon, Apple or Google.
2. From the Google Chrome **View** menu at the top of the screen, select **Developer** > **JavaScript Console**.
3. At the top of the console window, click on the **Network** tab.
3. On the Delta faucet page, click on the blue button labelled **Water Usage - This Week**
4. Expand the left side of the inspector window.
5. On the Name column, click on the result that starts with U**sageReport?macAddress=**
6. Copy the MAC Address as you will need to set it in the driver **Preferences** tab
7. On the **Headers** tab, under **Request Headers** you will find the required the full **Authorization** token needed.

**NOTE**: Copy the entire Authorization token **after** the word **Bearer**.

<img width="1279" height="618" alt="Screenshot 2025-12-26 at 1 48 27 PM" src="https://github.com/user-attachments/assets/a0c8ffda-c9c9-441e-8982-ebb3b7f28fc5" />


