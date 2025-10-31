## 1. Objective

The objective of this task was to conduct a comprehensive security audit of all installed browser extensions. The goal was to identify and remove any extensions that were suspicious, unnecessary, or posed a security risk due to excessive permissions, questionable origin, or malicious behavior, thereby enhancing overall browser security by minimizing the attack surface.

## 2. Methodology and Process

A systematic, multi-step audit process was conducted to evaluate each installed browser extension. The methodology was as follows:

* **Inventory:** A complete list of all installed extensions was compiled from the browser's extension management page (`chrome://extensions`).
* **Source Vetting:** The origin and reputation of each extension were investigated. This involved checking for browser-issued warnings, identifying the installation source (Official Web Store vs. third-party), and researching the developer's legitimacy.
* **Permission Audit:** The permissions requested by each extension were critically reviewed. Each permission was evaluated against the extension's stated functionality to determine if the access level was justified, following the principle of least privilege.
* **Risk Analysis and Action:** Based on the audit, extensions were categorized and appropriate action was taken. All extensions identified as high-risk were documented and removed. The browser was subsequently restarted to ensure all changes took full effect.

## 3. Findings and Actions Taken

The security audit identified two high-risk extensions that required immediate removal. The following sections detail the analysis and justification for their removal.

### Extensions Removed:

**Extension Name: 360 Internet Protection**

* **Analysis:** This extension was immediately flagged by Google Chrome's built-in "Safety Check" as potentially unsafe. The browser explicitly stated, "This extension violates the Chrome Web Store policy," and recommended its removal. Furthermore, the details revealed that the extension was "Added by a third-party," meaning it was not installed directly from the official Chrome Web Store, which is a significant security red flag.
* **Permission Risk:** The extension requested the permission to "read and change your data on sites." This is one of the most powerful and dangerous permissions an extension can have, as it grants the ability to monitor browsing activity, steal login credentials, and harvest personal information from any website visited.
* **Action Taken:** Removed. The combination of a direct policy violation warning from Chrome, a high-risk permission set, and a non-standard installation source made this extension an unacceptable security risk.

**Extension Name: McAfee® WebAdvisor**

* **Analysis:** Similar to the first extension, the details page indicated this extension was "Added by a third-party." This suggests it was likely bundled with other software and installed without explicit user consent, a common characteristic of Potentially Unwanted Programs (PUPs). While McAfee is a known security vendor, the installation method and the permissions requested were highly suspicious.
* **Permission Risk:** This extension requested an alarming number of broad and invasive permissions, including:
    * Read your browsing history
    * Block content on any page
    * Manage your downloads
    * Communicate with cooperating native applications
    * Allow this extension to read and change all your data on websites you visit
* These permissions grant the extension near-total control over the user's browsing experience and data, creating a massive potential for data exfiltration, session hijacking, and other malicious activities.
* **Action Taken:** Removed. The excessive and high-risk permissions, combined with its installation by a third party, far outweighed any potential security benefits. Such permissions violate the principle of least privilege and are not justifiable for its stated function.

## 4. Key Learnings and Reflections

This task provided critical hands-on experience in endpoint security and reinforced several core cybersecurity principles:

* **The Principle of Least Privilege:** The audit was a practical application of this fundamental concept. The most significant indicator of risk in both removed extensions was their request for permissions that were far too broad for any legitimate purpose.
* **The Importance of Source Vetting:** Both removed extensions were installed by a "third-party," bypassing the standard security checks of the official Chrome Web Store. This highlights the danger of bundled software and the critical need to only install extensions from official sources.
* **Heeding Browser Warnings:** Chrome's "Safety Check" feature proved to be an invaluable first line of defense, immediately identifying a policy-violating extension. This underscores the importance of paying close attention to security warnings issued by the browser itself.
* **The Browser as a Critical Endpoint:** This exercise demonstrated that the browser is a primary target for attackers. Securing it by diligently managing extensions is as critical as using traditional antivirus software, especially since malicious extensions can exfiltrate data over trusted channels that bypass network firewalls.
