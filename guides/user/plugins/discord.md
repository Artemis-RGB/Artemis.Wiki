---
title: Discord Plugin Guide
description: 
published: true
date: 2021-07-30T01:58:40.269Z
tags: 
editor: markdown
dateCreated: 2021-02-28T21:31:32.449Z
---

Since the Discord API only allows apps like Artemis to access local client information for 50 people at a time (on a whitelist), we had to instead allow each user to provide their own client ID and secret (which gets around this limitation). 

# Instructions

1. Download the latest version of the [Discord plugin](https://nightly.link/diogotr7/Artemis.Plugins/workflows/dotnet-core/master/Discord.zip) and save it anywhere to your PC
2. Import the plugin via **Settings** > **Plugins** > **Import plugin**
3. Go to the [Discord Developer Portal](https://discord.com/developers/applications).
4. Create a new Application.
![discord-guide_1.png](/guides/user/discord/discord-guide_1.png){.elevation-3 .radius-3}
5. Name it something you'll remember - "Artemis Integration" works fine. Click Create.
![discord-guide_2.png](/guides/user/discord/discord-guide_2.png){.elevation-3 .radius-3}
6. Optional - If you want, add an icon and fill in the description.
7. Go to the "OAuth2" tab ,click "Add Redirect" and paste `https://localhost/` *exactly*.
![discord-guide_3.png](/guides/user/discord/discord-guide_3.png){.elevation-3 .radius-3}
8. Click "Save Changes".
![discord-guide_3.png](/guides/user/discord/discord-guide_4.png){.elevation-3 .radius-3}
10. Here you'll also find the Client ID and Client Secret. Click on the "Copy" button under Client ID
11. Open Artemis, go into settings, and select the "Plugins" tab.
12. Look for the Discord Plugin and click the "Settings" button.
![discord-guide_5.png](/guides/user/discord/discord-guide_5.png){.elevation-3 .radius-3}
13. Paste the Client Id you copied previously.
![discord-guide_7.png](/guides/user/discord/discord-guide_7.png){.elevation-3 .radius-3}
14. Repeat the same procedure for the Client Secret. Use the "Copy" buttons in the discord web page to avoid adding extra spaces.
15. Click "Save Changes"
16. Disable and re-enable the Discord Artemis plugin.
17. Done!