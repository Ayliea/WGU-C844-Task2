# WLAN and Mobile Security Plan

## GRP1 Task 2



## Table of Contents

1. Introduction 1
   1.1 Authority 1
   1.2 Purpose and Scope 1
   1.3 Audience 2
   1.4 Document Structure 2
2. WLAN Vulnerabilities 2
   2.1 Rogue Access Points 2
   2.2. Evil Twins 3
3. Mobile Device Vulnerabilities 4
   3.1. Loss or Theft of Mobile Devices 4
   3.2. Wireless Eavesdropping 4
4. Mitigating WLAN Vulnerabilities 5
   4.1. 802.11i Authentication and Encryption 5
   4.2. User Training and Awareness Activities 5
5. Mitigating Mobile Device Vulnerabilities 6
   5.1. Using EMM Technologies 6
   5.1.1. EMM Implementation 6
   5.2. Encryption 7
   5.2.1. Encryption Implementation 7
   5.3. VPN 8
   5.3.1. VPN Implementation 8
6. Preventative Measure for WLAN Vulnerabilities 8
   6.1. Password Policy 8
7. Preventative Measure for Mobile Vulnerabilities 9
   7.1. Containerization 9
8. PCI DSS Explained 9
   8.1. Objective and Requirements for PCI DSS 9
   8.2. Compliance with PCI DSS 10
   8.3. Consequences of Non-Compliance 10
9. Recommended BYOD Approach 10
   References 11

# 1. Introduction

Alliah has recently experienced tremendous growth, expanding its operations and workforce. This growth has enabled the organization to improve its services and increase its revenue. However, with this expansion comes new challenges, particularly in wireless local area network (WLAN) and mobile device security. The organization must address WLAN and mobile device vulnerabilities that can propagate from this growth to ensure the safety and security of its network and the sensitive data within it.

## 1.1. Authority

This paper was written by a network professional at Alliah with extensive experience identifying and addressing wireless and mobile vulnerabilities. The author has a strong network security background and has worked with various organizations to secure their networks against threats.
The author has conducted a thorough analysis of Alliah's wireless and mobile systems and identified several vulnerabilities that could pose a significant security risk to the organization's security. These vulnerabilities include weak passwords, unsecured Wi-Fi networks, outdated software, unencrypted data transmissions, and inadequate network access control.
The author has developed solutions addressing each vulnerability to mitigate these risks. These solutions include implementing more containerization and robust password policies, using enterprise mobility management (EMM) technologies, implementing data encryption protocols and a virtual private network (VPN), and acquiring or developing a training and security awareness program.
By implementing these solutions, Alliah can significantly reduce the cyber-attack risk and prevent future threats to its wireless and mobile systems. The author is confident that these solutions will improve Alliah's overall security posture and help protect the organization's sensitive data and assets.

## 1.2. Purpose and Scope

The purpose of this paper is to identify the wireless and mobile vulnerabilities within Alliah's network and provide solutions to mitigate the associated risks. This paper addresses the security threats posed by wireless and mobile devices within the organization's infrastructure.
The scope of this paper is limited to the identification of wireless and mobile vulnerabilities and the provision of solutions to mitigate them. Additionally, this paper will not address specific devices but will suggest software solutions and provide general recommendations for improving the security of wireless and mobile devices.
This paper aims to raise awareness of the security risks associated with wireless and mobile devices and provide actionable recommendations to mitigate those risks and prevent future threats.

## 1.3. Audience

The intended audience for this paper is network professionals and Information Technology (IT) security personnel responsible for managing the organization's network infrastructure. The recommendations provided in this paper can be used as a starting point for developing a comprehensive security strategy that addresses wireless and mobile vulnerabilities within Alliah's network.

## 1.4. Document Structure

The remainder of this document is composed of the following sections and appendices:
• Sections 2 and 3 present overviews of WLAN and mobile device vulnerabilities, respectively, that Alliah can encounter and how malicious actors use these vulnerabilities to compromise information systems.
• Sections 4 and 5 provide recommendations for mitigating WLAN and mobile device vulnerabilities.
• Section 6 provides a preventative measure for WLAN vulnerabilities.
• Section 7 provides a preventative measure for mobile device vulnerabilities.
• Section 8 explains Payment Card Industry Data Security Standard (PCI DSS), highlighting its requirements for compliance and consequences for non-compliance.
• Section 8 provides the author’s recommendation for approaching a bring-your-own-device (BYOD) environment.

# 2. WLAN Vulnerabilities

Wireless Local Area Networks (WLANs) have become increasingly popular as technology advances. However, with this increase in usage comes an increase in vulnerabilities. WLANs are susceptible to various attacks, ranging from passive eavesdropping to active attacks. These vulnerabilities can lead to compromised sensitive information, unauthorized network access, and even complete network shutdowns. Understanding these vulnerabilities is crucial in protecting a network from potential threats. This section will overview some of the most common WLAN vulnerabilities.

## 2.1. Rogue Access Points

As Alliah grows and expands, it becomes more vulnerable to rogue access points (AP). A rogue access point is an unauthorized access point connected to a wired network. Rogue access points can provide easier access to a network, whether the intention is malicious or not. Threat actors can use a rogue AP to extend their area of operation to a safer location. In addition, they can use the AP to increase the attack surface of a network, creating a convenient backdoor and leaving more exploitable vectors open for use. Individuals with less malicious intentions, such as employees, may use a rogue AP for more convenient access to the network. Rouge APs from employees can also leave the network vulnerable to unauthorized access, as these individuals will probably install the AP poorly (Doherty, 2021, p.130).
The installation of rogue APs can lead to the following vulnerabilities:
• Man-in-the-middle (MITM) attacks
• Address resolution protocol (ARP) poisoning, dynamic host configuration protocol (DHCP) attacks, and other wired network attacks
• Free access to a private network
• Data leakage and theft
• Scanning and mapping of the WLAN network
Consider the following hypothetical: an attacker bypasses Alliah’s physical security measures and sets up a rogue AP within the organization’s network. The AP appears legitimate but is controlled by the attacker. Employees connect with the rogue AP, allowing the attacker to launch phishing attacks, malware distribution, and man-in-the-middle attacks. Using one or more attacks, the attacker locates and exfiltrates sensitive information from Alliah’s servers.
The hypothetical outlines a potential incident Alliah will have to address if it does not take preventative measures against rogue access points.

## 2.2. Evil Twins

Evil twins are another threat to Alliah’s WLAN. An evil twin is a fraudulent access point that masquerades as a legitimate access point by cloning a legitimate access point's media access control (MAC) address and service set identifier (SSID) (Ledesma, 2022). A malicious actor can trick users into connecting their client to it by configuring this AP to masquerade as a legitimate AP. An actor can also connect these clients to the evil twin without user interaction by listening to them to see what SSID they are searching for. After connection, the client is vulnerable to a wide range of network attacks (Doherty, 2021, p.130).
In what scenario could Alliah fall victim to an evil twin attack? Like the hypothetical outlined in section 1.1, an attacker bypasses Alliah’s physical security measures and sets up an evil twin in a location where the WLAN’s signal is weakest. Before, employees had to deal with decreased performance or move to a location on-site that was closer to an access point. Employees now see a new access point installed that extends the WLAN into the area. This access point has the same MAC address and SSID as they are used to, so how could this AP not be legitimate?

The employees connect their clients to the AP. The more skeptical employees opt not to connect, but the attacker crosses this roadblock by listening to what SSID the clients are searching for. Now, the attacker has unauthorized access to many devices and can exfiltrate sensitive information.
This scenario highlights the ease with which Alliah can fall victim to an evil twin attack.

# 3. Mobile Device Vulnerabilities

Mobile devices have become integral to our daily lives, and businesses have embraced them to enhance productivity and communication. However, the increasing use of mobile devices has also led to an increase in mobile device vulnerabilities. As an organization, Alliah must take proactive measures to protect its mobile devices from potential cyber-attacks. This document outlines types of mobile device vulnerabilities.

## 3.1. Loss or Theft of Mobile Devices

People remain the biggest security threat to organizations. For this reason, though not as technical as most other vulnerabilities, the loss or theft of mobile devices is one of the most common vulnerabilities to organizations utilizing a BYOD policy. Device loss can cause data loss and potentially unauthorized system access (Doherty, 2021, p.128).
GridWorks IC was a victim of this vulnerability. A vendor hired by Health Share of Oregon, GridWorks IC provided non-emergent medical transportation for Health Share of Oregon. On January 2, 2020, the vendor suffered a break-in, and a laptop was stolen. This event exposed the personally identifiable information (PII) of 654,362 members (Osborne, 2020). Information such as names, addresses, social security numbers, and Medicaid ID numbers were compromised in the breach.

## 3.2. Wireless Eavesdropping

Improperly secured devices pose the risk of exploitation, even when doing something as simple as visiting an unsafe webpage. A malicious actor can direct users to a webpage that installs malware or performs another action on the device (Doherty, 2021, p. 127). This is a significant issue for Alliah, as their BYOD policy leaves users’ devices open to vulnerabilities because of a lack of mandated updates. In addition, the access point on the patio makes eavesdropping on the network easier for the attacker. All the attacker needs is a wireless network adapter and a sniffer tool to capture sensitive traffic on the network, like login credentials, financial data, and personal information.

# 4. Mitigating WLAN Vulnerabilities

Wireless Local Area Network (WLAN) vulnerability is a growing concern for organizations like Alliah. With the increasing number of cyber threats, it is essential to implement proper security measures to protect the organization's network and data. WLAN vulnerability mitigation techniques can help reduce the risk of cyber-attacks and ensure the organization's assets' confidentiality, integrity, and availability. This section will discuss some critical WLAN vulnerability mitigations that Alliah can implement to safeguard its network.

## 4.1. 802.11i Authentication and Encryption

To address the vulnerabilities specified in section A, Alliah should implement 802.11i authentication and encryption on the WLAN. 802.11i is a security protocol that provides advanced security features for WLANs. It uses the Advanced Encryption Standard (AES) to protect sensitive data from compromise. AES is a widely used encryption algorithm used to encrypt electronic data. It provides confidentiality by ensuring unauthorized parties cannot intercept and read sensitive data transmitted over the WLAN (Frankel et al., 2007).
Also, it provides robust authentication by requiring users to provide a valid username and password or other credentials before accessing the WLAN. The authentication process verifies the user’s identity, ensuring only authorized users can access the network.
Finally, it provides data integrity, which ensures that data has not been modified or corrupted in transit. Data integrity is crucial for ensuring the accuracy and reliability of data transmitted over the WLAN.
Alliah must implement 802.11i to reduce the possibility that unauthorized parties can connect rogue access points and evil twins to the enterprise network. This, in turn, will help improve the organization’s overall security posture and protect critical assets from potential security threats.
Having 802.11i authentication and encryption on the WLAN will be especially important for the patio area of Alliah’s site, as having an access point covering this location makes the WLAN more accessible to unauthorized parties. 802.11i prevents these parties from accessing the network and company resources without proper authentication.

## 4.2. User Training and Awareness Activities

User training and awareness activities are effective measures for increasing the security posture of the WLAN environment. Users are often the weakest link in the security chain, as without proper training, malicious actors can manipulate them to introduce exploitable vulnerabilities. With training, users become more informed about the potential risks and threats to a WLAN environment. In addition, such training can create a security culture amongst users. They will become more aware of their role in ensuring company data security. This incentivizes users to take their role seriously and follow security best practices (Wilson et al., 1998, pp. 15-16).
User training is essential for Alliah, as it must educate users on the potential for rogue access points and evil twins on their premises. Proper education on these threats will reduce the likelihood of an employee installing a rogue access point or connecting to an evil twin. Alliah can provide training sessions, newsletters, and other resources to educate employees on identifying and avoiding these security risks. By taking proactive measures to prevent the occurrence of these threats, Alliah can ensure the safety and security of its network and data.
SANS Institute offers security awareness training solutions for organizations that wish to change user behavior and reduce the risk of exploitation. In addition, The Computer Security Act of 1987 mandated the National Institute of Standards and Technology (NIST) and Office of Personnel Management (OPM) to create guidelines on computer security awareness and training based on functional organizational roles. These guidelines, available in NIST Special Publication (SP) 800-16, can assist Alliah in developing its computer security awareness training. Typical training includes phishing simulations and regular security reminders.

# 5. Mitigating Mobile Device Vulnerabilities

Introducing mobile devices into business operations has created new security risks, especially for organizations like Alliah that adopt BYOD policies. The sensitive information transmitted and stored on these devices makes them attractive targets for cybercriminals. To mitigate these risks, Alliah needs to implement mobile device vulnerability mitigations that protect against potential threats and prevent unauthorized access to sensitive data. This document outlines the critical mobile device vulnerability mitigations that Alliah should consider implementing to enhance its cybersecurity posture.

## 5.1. Using EMM Technologies

As recommended in NIST SP 800-124r2, Alliah can address the vulnerabilities specified in section B by implementing EMM technologies. These technologies help secure mobile devices by providing a centralized platform for managing and monitoring mobile devices, applications, and data. Alliah can use EMM technologies and their advanced security features to enforce security policies on mobile devices. EMM enables administrators to block unauthorized applications, control website access, lock and wipe lost or stolen devices and prevent misconfigured devices from accessing organizational resources. These features help to ensure that confidential data remains secure even if the device falls into the wrong hands.

## 5.1.1. EEM Implementation

To implement EMM technologies, Alliah can use various tools, such as Mobile Device Management (MDM), Mobile Application Management (MAM), and Mobile Information Management (MIM). MDM tools provide device inventory, remote device management, and policy enforcement. MAM tools provide application distribution, configuration, and policy enforcement. MIM tools provide data security with encryption, data loss prevention, and secure file sharing (What Is Enterprise Mobility Management (EMM)? | VMware, 2023).
To implement EMM technologies, Alliah should consider the following steps:
• Define the security policies and requirements for mobile devices.
• Select and implement the appropriate EMM tools for the organization’s needs.
• Train the administrators and end-users on using the EMM tools and security policies.
• Continuously monitor and update the EMM tools and security policies to ensure the security of mobile devices.
VMware AirWatch, Ivanti MobileIron, and Citrix Endpoint Management are examples of EMM solutions Alliah can use.

## 5.2. Encryption

Alliah can further address mobile device vulnerabilities by properly encrypting data at rest and in transit. It must do so to comply with data security regulations and protect customer data. It also must do so to protect its intellectual property. Encryption is essential for organizations with a remote workforce, as workers access company data from different locations and devices. This increases the risk of data breaches and compromise from lost or stolen devices (Souppaya, 2023).

## 5.2.1. Encryption Implementation

To implement strong encryption, Alliah should consider the following steps:
• Identify data that must be encrypted.
• Choose the suitable encryption standard for protected data.
• Develop appropriate encryption policies and procedures.
• Train employees in encryption best practices.
• Continuously test implemented encryption systems to ensure they are working effectively.
Today, the most used encryption standards are Triple Data Encryption Standard (3DES), AES, and Rivest-Shamir-Adleman (RSA). AES is recognized and recommended by the US government.

## 5.3. VPN

Alliah can also encrypt data in transit using a virtual private network (VPN). According to NIST SP 800-113, VPNs are critical for organizations to maintain the confidentiality, integrity, and availability of information and information systems. They create a secure tunnel between authorized devices and the organization’s network by encrypting data in transmission between the two. Secure communication can protect against eavesdropping, man-in-the-middle attacks, and data leakage. A secure tunnel is vital for Alliah, as employees frequently access company resources off-site.

## 5.3.1. VPN Implementation

To implement a VPN, Alliah should consider the following steps suggested by NIST SP 800-113:
• Identify the current and future requirements for remote access and determine how the organization can use a VPN to meet them.
• Design the VPN solution.
• Implement and test a prototype of the VPN solution in a testing environment.
• Deploy the tested VPN solution.
• Manage the solution throughout its lifecycle.

# 6. Preventative Measure for WLAN Vulnerabilities

Alliah, like any other organization, faces security risks in its wireless local area network (WLAN). WLANs are vulnerable to attacks like rogue access points and evil twins. Failure to address WLAN vulnerabilities can result in data breaches, financial loss, and reputation damage. The organization must implement preventative measures to safeguard Alliah's WLAN and protect against security threats. This section outlines a preventative measure that Alliah can take to secure its WLAN.

## 6.1. Password Policy

To increase the security posture of its WLAN environment, Alliah must implement strict password requirements, such as a minimum password length, maximum age, special character usage, and password reuse. A policy shields confidential data from brute force attacks and data breaches. It also promotes good security practices amongst employees, creating a culture of security awareness.
This password policy will also help Alliah comply with the Payment Card Industry Data Security Standard (PCI DSS). PCI DSS mandates cybersecurity controls and business practices that companies that process credit card payments must implement. Compliance is essential for Alliah to maintain its reputation and avoid hefty fines and legal action. PCI DSS requires that organizations implement strong access control measures by using unique user IDs and strong passwords to restrict access to cardholder data (Fruhlinger, 2022).

# 7. Preventative Measure for Mobile Device Vulnerabilities

Alliah recognizes mobile devices' importance as critical communication and productivity tools. However, these devices pose a significant risk to the organization's security, as they are prone to vulnerabilities such as loss or theft and wireless eavesdropping. Therefore, it is essential to implement preventative measures to ensure Alliah's mobile devices and data safety. This document outlines the measures that Alliah must take to prevent mobile device vulnerabilities.

## 7.1. Containerization

Alliah must also implement preventative measures for the mobile environment. One of the most effective measures for increasing the environment’s security posture is containerizing company data. According to NIST-1800-22 and NIST SP 800-124r2, company and personal data must be separate. Since data travels outside internal networks with BYOD device deployments, a secure container to isolate enterprise data is an effective strategy to prevent data compromise. Implementing isolation mechanisms can prove costly but benefit organizational data's overall security.
Containerization can be a valuable tool for meeting several of the requirements outlined in PCI DSS. For example, Alliah can use containers to isolate sensitive data from unauthorized parties, reducing the risk of unauthorized access or disclosure. The organization can also configure them to meet security requirements, such as encryption, access controls, and network segmentation.

# 8. PCI DSS Explained

Previously, we mentioned the importance of remaining PCI DSS compliant. It is a set of security standards major credit card companies created to safeguard against credit card fraud and protect sensitive information. The PCI DSS standard applies to all entities storing, processing, or transmitting cardholder data. This includes merchants, financial institutions, and service providers.

## 8.1. Objective and Requirements of PCI DSS

The primary objective of PCI DSS is to ensure that cardholder data is protected from unauthorized access and misuse. The standard aims to reduce the risk of credit card fraud, prevent breaches, and protect the industry’s reputation. The specific requirements of PCI DSS, as defined by Josh Fruhlinger of CSO, are as follows:

1. Install and maintain network security controls to prevent unauthorized system access.
2. Apply secure configuration to all system components.
3. Protect stored account data.
4. Use strong cryptography when transmitting cardholder data across open, public networks.
5. Protect systems and networks from malicious software.
6. Develop and maintain secure systems and applications.
7. Restrict access to cardholder data by business need-to-know.
8. Identify users and authenticate access to system components.
9. Restrict physical access to cardholder data.
10. Log and monitor all access to network resources and cardholder data.
11. Regularly test security systems and processes.
12. Maintain a policy that addresses information security.

## 8.2. Compliance with PCI DSS

PCI DSS compliance is mandatory for all organizations that handle credit card information. Compliance is assessed by a Qualified Security Assessor (QSA), who conducts an on-site audit of the organization's systems and procedures. Organizations must demonstrate compliance with all 12 requirements of PCI DSS to be considered fully compliant.

## 8.3. Consequences of Non-Compliance

Organizations that fail to comply with PCI DSS can face significant consequences, including fines, legal action, and termination of the ability to process credit card payments. Non-compliance can also damage the organization's reputation and cause a loss of customer trust.

# 9. Recommended BYOD Approach

BYOD policies remove most upfront administrative costs associated with supplying devices to employees. However, BYOD leaves Alliah and its data vulnerable to compromise. Until Alliah sees enough net profit to afford conversion from a BYOD policy to a CYOD, COPE, or COBO policy, it should mitigate the security risks its experiencing. It can do so by implementing Enterprise Mobility Management technologies like MDM, MIM, and MAM. These technologies can regulate devices and their compliance with company policies. Next, devices must have a strict password policy and multi-factor authentication. Alliah must also use containerization to separate company data from personal data and VPNs to protect sensitive data in transit. Finally, Alliah should either acquire a security awareness training solution from an organization like the SANS Institute or use NIST 800-16 to assist in developing their solution. While no combination of methods is bulletproof, taking these steps will increase the organization’s security posture and give it more room to adjust to growth.

References
Boeckl, K. (2022, November 29). Mobile Device Security: Bring Your Own Device (BYOD) (2nd Draft). https://csrc.nist.gov/publications/detail/sp/1800-22/draft
Computer Security Division, Information Technology Laboratory, National Institute of Standards and Technology, U.S. Department of Commerce. (n.d.). Awareness, Training, & Education | CSRC | CSRC. https://csrc.nist.gov/Projects/Awareness-Training-Education
Doherty, J. (2021, April). Wireless and mobile device security. Jones & Bartlett Learning, LLC.
Frankel, S. E., Eydt, B., Owens, L., & Scarfone, K. A. (2007). Establishing wireless robust security networks : https://doi.org/10.6028/nist.sp.800-97
Frankel, S. E., Hoffman, P., Orebaugh, A., & Park, R. S. (2008). Guide to SSL VPNs. https://doi.org/10.6028/nist.sp.800-113
Fruhlinger, J. (2022, May 16). PCI DSS explained: Requirements, fines, and steps to compliance. CSO Online. https://www.csoonline.com/article/3566072/pci-dss-explained-requirements-fines-and-steps-to-compliance.html
IBM Documentation. (n.d.). https://www.ibm.com/docs/hr/sgklm/4.1?topic=overview-cryptographic-algorithm-key-length
Keysight. (2022, July 14). BYOD Mitigation Starts in the WLAN. Keysight. https://www.keysight.com/us/en/assets/3120-1055/white-papers/BYOD-Mitigation-Starts-in-the-WLAN.pdf?success=true
Ledesma, J. (2022, June 29). Evil Twin Attack: What it is, How to Detect & Prevent it. Data Security. https://www.varonis.com/blog/evil-twin-attack

Osborne, C. (2020, February 6). Health Share of Oregon discloses data breach, theft of member PII. ZDNET. https://www.zdnet.com/article/health-share-of-oregon-discloses-data-breach-theft-of-member-pii/
Robb, D. (2023). Best Enterprise Mobility Management (EMM) Solutions. eSecurityPlanet. https://www.esecurityplanet.com/products/enterprise-mobility-management/
Souppaya, M. (2023). Guidelines for Managing the Security of Mobile Devices in the Enterprise. https://doi.org/10.6028/nist.sp.800-124r2
Souppaya, M., & Scarfone, K. A. (2012). Guidelines for securing Wireless Local Area Networks (WLANs). https://doi.org/10.6028/nist.sp.800-153
What is encryption and how does it protect your data? (n.d.). https://us.norton.com/blog/privacy/what-is-encryption
What is Enterprise Mobility Management (EMM)? | VMware. (2023, March 14). VMware. https://www.vmware.com/topics/glossary/content/enterprise-mobility-management.html
Wilson, M., De Zafra, D. E., Pitcher, S., Tressler, J., & Ippolito, J. (1998). Information technology security training requirements : https://doi.org/10.6028/nist.sp.800-16
