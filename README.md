🎯 Mission Objective

Perform a manual security audit of installed browser extensions to identify hidden risks, excessive permissions, and potential abuse vectors. The goal is to understand how malicious or poorly designed extensions can compromise user privacy, steal sensitive data, and weaken browser security.

🧰 Environment & Tools

Browser: Microsoft Edge (Chromium-based)

Audit Type: Manual Extension Inspection

Methodology: Permission analysis, source validation, functionality review

🔍 Recon Phase – Extension Enumeration

All installed browser extensions were enumerated via the extension manager. The following extensions were discovered:

McAfee® WebAdvisor

Google Docs Offline

WebCRX

Each extension was treated as a potential attack vector and analyzed individually.

🧪 Analysis Phase – Extension Deep Dive
1️⃣ McAfee® WebAdvisor

Source: Microsoft Edge Add-ons Store (Trusted)

Functionality:

Real-time protection against malicious websites

Download reputation analysis

Phishing and malware prevention

Permissions Observed:

Read browsing history

Block content on webpages

Manage downloads

Communicate with native applications

Security Analysis: At first glance, these permissions appear excessive. However, from a defensive security standpoint, such privileges are required for effective threat detection and traffic inspection. The extension is maintained by a well-known security vendor and showed no signs of malicious behavior.

Verdict: ✅ Legitimate defensive extension
✅ Permissions justified by functionality
Status: Kept installed

2️⃣ Google Docs Offline

Source: Google (Trusted Vendor)

Functionality:

Enables offline access to Google Docs

Permissions Observed:

Minimal and limited to document access

Security Analysis: This extension operates within a narrow scope and does not request unnecessary permissions. No abnormal background activity or data exfiltration risk was identified.

Verdict: ✅ Trusted and safe
Status: Kept installed

3️⃣ WebCRX

Source: Chrome Web Store

Functionality:

Enables installation of local .crx extension files

Permissions Observed:

Ability to read and change data on visited sites

Security Analysis: While WebCRX is not inherently malicious, its core functionality allows installation of extensions outside standard browser store security validation. This creates a security bypass scenario, commonly abused in real-world attacks to deploy trojanized or modified extensions.

From a red-team perspective, such tools significantly expand the browser attack surface if left uncontrolled.

Verdict: ⚠️ Not malicious by default
⚠️ High abuse potential if misused
Status: Removed as a precaution

🔄 Mitigation Actions Taken

Reviewed all installed extensions

Verified sources and developers

Audited permission scopes

Identified potential attack vectors

Removed unnecessary / risky extension

Restarted browser to enforce changes

☠️ Threat Intelligence – How Malicious Extensions Attack

Malicious or compromised browser extensions can:

Steal saved passwords and credentials

Monitor keystrokes and form inputs

Track browsing behavior and user profiling

Inject malicious ads or scripts

Redirect users to phishing websites

Perform unauthorized background operations

🧠 Security Lessons Learned

Browser extensions operate with high privileges inside the browser sandbox

Even legitimate extensions can become threats if misused

Least-privilege principle is critical for extension security

Regular extension audits reduce long-term risk

📌 Final Outcome

No active malicious extensions detected

One potentially risky extension identified and mitigated

Browser security posture improved

Increased awareness of extension-based attack vectors

📂 Repository Structure

Task-7-Browser-Extension-Security/
├── README.md
├── screenshots/
│ ├── extensions_list.png
│ ├── mcafee_details.png
│ └── webcrx_details.png



🧑‍💻 Conclusion

Browser extensions are powerful tools—but power comes with risk. Continuous monitoring, permission auditing, and security awareness are essential to prevent extension-based attacks and protect user data.
