---
title: Frequently Asked Questions
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

## How to enable Teleporting or Color Changing? (Or any other extra CSP Server Function)
Read [this CSP wiki page](https://github.com/ac-custom-shaders-patch/acc-extension-config/wiki/Misc-%E2%80%93-Server-extra-options#freeroam-features) carefully. Everything you want to add goes into `cfg/csp_extra_options.ini` on your server.  
**If the file doesn't exist yet, create it yourself. For example:**  
![](./assets/oxp4a21.png)    
Place the file in the `cfg` folder of your server. If you're running your server via Content Manager, click the `Folder` button and place it there instead.   

For teleporting, two other things have to be done:
* Requiring a minimum CSP version
* Allowing cars in the entry list to teleport

Depending on if you have the full version of Content Manager or not, there are two different ways to accomplish this:

<Tabs>
<TabItem value="content-manager" label="Content Manager (full)" default>

  In the `Main` tab of your server check `Require CSP to Join`:  
  ![](./assets/HxAVvsd.png) 
  
  Check `Allow teleporting` for each car on your entry list:  
  ![](./assets/Il4RrjG.png)

</TabItem>
<TabItem value="manual" label="Manual">

  * In `content/tracks` of your server, create a new folder called `csp`
  * Move your track folder into `content/tracks/csp`
  * In `server_cfg.ini` change the path of your track like this: `TRACK=csp/<CSPversionID>/../<trackname>`, for example `TRACK=csp/1937/../shuto_revival_project_beta`
  * In `data/surfaces.ini` of your track, change `SURFACE_0` to `CSPFACE_0`
  * In your `entry_list.ini` add `/ADAn` to the end of each skin, for example `SKIN=<skinname>/ADAn`

  |Option||
  |---|---|
  |`/ABAH`|Allow only Color Changing|
  |`/ACA3`|Allow only Teleporting|
  |`/ADAn`|Allow Both|

</TabItem>
</Tabs>

## Does anyone have the teleport locations for SRP?
Either use the [official SRP teleports](https://discord.com/channels/890676433746268231/890676434245419031/937681626152980491) or make some yourself with Objects Inspector or [this app](https://www.racedepartment.com/downloads/comfy-map.52623/).  

## How do I get dense traffic?
* Use more traffic slots
* Decrease `MinAiSafetyDistanceMeters` / `MaxAiSafetyDistanceMeters` to make gaps between AI cars smaller
* Depending on how many people are on your server you could increase `AiPerPlayerTargetCount` / `MaxAiTargetCount` 