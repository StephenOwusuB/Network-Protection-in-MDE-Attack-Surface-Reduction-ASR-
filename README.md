# Network Protection in MDE Attack Surface Reduction (ASR)

Network protection is one of the features of the Attack Surface Reduction (ASR) feature. It helps stop attacks from harmful websites and prevents tricking you into downloading malicious software. It works not only for web browsers but also for other browsers as well. It leverages Microsoft Defender SmartScreen and extends its capabilities to block HTTPS traffic to potentially harmful domains.

## Web Protection Features

Web protection covers three main features:
1. Web Threat Protection
2. Custom Indicators
3. Web Content Filtering

For all of these to work, SmartScreen must be enabled, and Network Protection must be in block mode.

## Setting Custom Indicators

1. Scroll down to **Settings**.
2. Select **Endpoint**.
3. Scroll down to **Rules**.
4. Under Rules, select **Indicators**.
5. You will see file hashes, IP addresses, URLs/Domains, and Certificates.

## Web Content Filtering

1. Scroll down and select **Web Content Filtering**.
2. Click on **Add Policy** to add a policy.
3. Specify the name for the web content filtering.
4. Under **Block Categories**, select the category you would like to block.

Network protection can block either URLs or IP addresses. It uses the database of SmartScreen to protect your devices from known malicious URLs. It can:
- Block IP/URL addresses from your own threat intelligence custom indicators.
- Block unsanctioned services from Microsoft Defender for Cloud Apps.
- Block browser access to websites based on category (Web Content Filtering).
- Block Command and Control (C2) content.

When a user accesses a website, the following takes place:
1. Known good reputation is set to **Allowed**.
2. Unknown or uncertain reputation is set to **Audit**, which allows the user to access or unblock the domain or URL. (The user gets **OK**, **Unblock**, **Feedback**. If the user selects **OK**, the domain or URL is blocked. If the user selects **Unblock**, the webpage is released for the user to access for 24 hours and then it is blocked again.)
3. Known bad (malicious) reputation is set to **Block**. The user gets a pop-up to select either **OK** or **Feedback**. If the user selects **OK**, the connection is ended. If the user selects **Feedback**, they will have the option to create a ticket. There's no unblock option.

## Adding Indicators to Control Access to URLs

1. Under **Indicators**, select the **URL** tab and click on **Add Item**.
2. Specify the URL/Domain.
3. Specify the title.
4. Provide a description to assist another admin in understanding why this is an indicator.
5. Select when this indicator should expire. Keep in mind that it is in UTC. When you select **Never**, it will never expire. When you select **Custom**, you can specify the date you want it to end.
6. Click on **Show Statistics** to give you threat intelligence information about this URL.
7. Select the action you want to take place when the URL/Domain is found. Options are **Allow**, **Audit**, **Warn**, or **Block Execution**.
   - **Allow** means the user can access that URL.
   - **Audit** means the user can access the URL, but an event log will be generated in the Windows Event Log.
   - **Warn** means it will block the access, but it will give the user the option to unblock it.
   - **Block Execution** means users cannot access that malicious URL or Domain.

### Setting Up Policies

If you select **Allow**:
1. Click on **Next**. You will have the option to specify the group of users to apply this on.
2. After specifying the group, click on **Next**. You will see a summary of the policy. Click **Submit** to add this policy.

If you select **Audit**:
1. Click on **Next**. You will have the option to select the severity and the category.
2. Specify recommended actions. Click **Next** to specify the device group's scope, and click **Next**.
3. You will see a summary of the policies. Click **Submit** to save it.

If you select **Warn**:
1. Click on **Next**. You will have the option to select the bypass duration. This determines how often a user should be warned.
2. Add a user notification custom URL to provide more information to the user about the indicator.
3. Select the severity, category, and recommended actions. Specify the device group's scope. Click **Next**, and you will see a summary. Click **Submit** to add the policy.

If you select **Block Execution**:
1. Click on **Next**. Specify the severity, category, and recommended actions.
2. Click **Submit** to save the policy.

## Enabling, Disabling, and Auditing Network Protection in Power
