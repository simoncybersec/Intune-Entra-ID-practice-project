## **Project Scenario: Securing a Small Nonprofit's Devices and Users with Intune & Entra ID**

### **🏢 Background**

You're the volunteer IT administrator at *SerFix Foundation*, a small nonprofit organization with 5 staff members and several volunteers. The team uses various devices (Windows 11, macOS, iPhone, Androids) to access sensitive data including donor information, health forms, and internal communications.

Your task is to **set up secure, compliant, and productive access** to company resources using **Microsoft 365 Business Premium**, **Microsoft Intune**, and **Microsoft Entra ID**.

---

## **✅ Project Plan with 5 Phases**

---

### **🔹 Phase 1: Initial Tenant Setup**

**Goal:** Build your cloud identity foundation.

1. **Log in to Admin Center**  
    [https://admin.microsoft.com](https://admin.microsoft.com)

   * Customize your org: Name, logo, domain (optional).

2. **Create 5 user accounts**  
    Go to **Users \> Active users \> Add a user (to add individual user)**

   Go to **Users \> All users \> Bulk operations \> Bulk create.** The Bulk create users pane is displayed, which provides an option to Download a CVS template you can use **(To add multiple users).** 

   When your CVS template is ready, use the browse functionality to locate and upload the file. Select Submit to begin the import.

     
    Example users:

   * Dina@SerFix739.onmicrosoft.com  
   * bjones@SerFix739.onmicrosoft.com  
   * awilson@SerFix739.onmicrosoft.com  
   * jdoe123@SerFix739.onmicrosoft.com  
   * ssmith@SerFix739.onmicrosoft.com  
   * simeb20@SerFix739.onmicrosoft.com  
   * klee@SerFix739.onmicrosoft.com  
   * gsimon@SerFix739.onmicrosoft.com  
   * [tbrown@SerFix739.onmicrosoft.com](mailto:tbrown@SerFix739.onmicrosoft.com)  

**Note**: *Adding a user in Entra ID (formerly Azure Active Directory) is fundamentally the same as adding a user in the Microsoft 365 admin center, as they both manage the same underlying user store, which is Entra ID. When a user is created in the Microsoft 365 admin center, it's also created in Entra ID, and vice versa.* 

3. **Assign Business Premium licenses**

   * Assign to each user during creation or afterward via “Licenses and apps.”
  ![3](https://github.com/user-attachments/assets/fc182e6a-eeaa-4548-b90c-0f91d0ec8410)
  ![4](https://github.com/user-attachments/assets/f2b6e074-8cbb-45df-9f0d-d8984154d265)

  
4. **Assign Roles**  
    In **Microsoft Entra \> Roles and administrators**, assign:

   * **Simon**: Global Administrator

   * **Dina**: AI Administrator

   * **Others**: Standard users
     ![5](https://github.com/user-attachments/assets/71841756-5774-45ac-ab8e-143fd882d972)


5. **Enable MFA for all users**

   * Go to **Entra ID \> Users \> Per-user MFA**
     ![6](https://github.com/user-attachments/assets/6f6d83ec-71f3-4d91-89e0-59d00ce64f71)

   * Enforce MFA
     ![7](https://github.com/user-attachments/assets/7c21dedb-0caa-4f21-a912-962357b8dd1d)

   * On each device, install **Microsoft Authenticator** and test login with MFA prompts

---

### **🔹 Phase 2: Configure Intune for Device Management**

**Goal:** Enroll a variety of devices for management and protection.

1. **Access Microsoft Intune Admin Center**  
    [https://intune.microsoft.com](https://intune.microsoft.com)

2. **Set up Enrollment Methods**

   * **Windows**:  
      Go to **Devices \> Enroll devices \> Automatic enrollment**  
      Confirm it's enabled via Azure AD Join.
     ![8](https://github.com/user-attachments/assets/b8d62395-9a45-4cf7-a079-9c71ba712fe2)
     
     ![9](https://github.com/user-attachments/assets/e46407f0-a76a-4718-84e2-1656f9e7162b)



   * **macOS**:  
      Manual enrollment (or ABM if available).
     ![10](https://github.com/user-attachments/assets/589e1808-3943-409a-8118-718cafa45c11)
     ![11](https://github.com/user-attachments/assets/4acb3b1f-1014-4972-a74d-f0bc46db9af9)


   * **iPhone & Android**:  
      Install the **Company Portal app** from App Store/Google Play.
     ![12](https://github.com/user-attachments/assets/982b7450-8046-4339-8974-825b823d2c7f)


3. **Enroll Each Device [https://learn.microsoft.com/en-us/intune/intune-service/user-help/enroll-your-device-in-intune-macos-cp](https://learn.microsoft.com/en-us/intune/intune-service/user-help/enroll-your-device-in-intune-macos-cp)** 

   * **Windows 11**:  
      Go to **Settings \> Accounts \> Access work or school \> Connect**  
      Sign in with a user account. Verify it appears in Intune \> Devices.
     ![13](https://github.com/user-attachments/assets/0c76b04e-e4bd-45bb-b2fc-6c917d85bb5e)
     ![14](https://github.com/user-attachments/assets/813949bf-1d24-4df0-85ba-e9e4f59b4c4c)
     ![15](https://github.com/user-attachments/assets/d5fee9f5-a6fe-4464-bda1-d5c7d4837686)
     ![16](https://github.com/user-attachments/assets/5b5355f3-8cd9-4e06-b3c5-e840691b85da)
     ![17](https://github.com/user-attachments/assets/3dbbf516-152e-4126-b9ad-708e45e5ed1e)
     ![20](https://github.com/user-attachments/assets/09cba409-bf3a-430e-9335-a5684cd81a87)

   * **macOS**:  
      Open **Company Portal**, sign in with a test user, follow instructions.
     ![mac1](https://github.com/user-attachments/assets/8a3cff14-6434-4b1b-84a4-dd610c9528e3)
     ![mac2](https://github.com/user-attachments/assets/8778dc76-5f81-4f67-b7d0-6393ee070e09)
     ![mac3](https://github.com/user-attachments/assets/ac850ca7-94e8-490a-b4ef-0863de84dad9)

   * **iPhone/Android**:  
      Use different users, open **Company Portal**, enroll and approve permissions.
     ![andr1](https://github.com/user-attachments/assets/1c68c126-e42b-4a1c-b21d-306ed5133c82)
     ![andr2](https://github.com/user-attachments/assets/f5910faf-09bc-4dd2-9345-628a129fab4d)
     
---

### **🔹 Phase 3: Policy Management (Compliance & Configuration)**

**Goal:** Define secure and compliant rules for devices.

1. **Create Device Compliance Policies**

   * Go to **Devices \> Compliance policies \> Create policy**
   ![pol1](https://github.com/user-attachments/assets/39ced923-3dd4-4abb-9c71-10d2427f2563)
   ![pol12](https://github.com/user-attachments/assets/ffc97054-8b63-4c43-b629-fe1038ed48a6)
![pol11](https://github.com/user-attachments/assets/6f486895-af94-47f5-9f2b-f8381ca34ef2)
![pol10](https://github.com/user-attachments/assets/5877a991-6a29-4b01-bc8f-700e291b1e0f)
![pol9](https://github.com/user-attachments/assets/947d705a-41dc-428b-b32b-00f98336dc9e)
![pol8](https://github.com/user-attachments/assets/fd0d2c61-acb2-4f70-8e9e-e7805a0c208e)
![pol7](https://github.com/user-attachments/assets/95494234-bd8f-4e9c-9c4e-de6775174734)
![pol6](https://github.com/user-attachments/assets/4ac22182-cef2-44c4-81ab-448c2d43b00e)
![pol5](https://github.com/user-attachments/assets/4ec2d7d8-bc48-43de-834d-976722b1a35d)
![pol4](https://github.com/user-attachments/assets/f3e4f0a8-61e2-4613-b512-c17adcbe1220)
![pol3](https://github.com/user-attachments/assets/386e3115-659e-42d4-87c2-c6124874b933)
![pol2](https://github.com/user-attachments/assets/d31be313-3917-40e6-865f-d44f02779dee)

   * Platform: Windows, iOS, Android, macOS

   * Sample rules:

     * Require password

     * Block rooted/jailbroken

     * Require device encryption

2. **Create Configuration Profiles**

   * Go to **Devices \> Configuration profiles \> Create**
  ![pol13](https://github.com/user-attachments/assets/725a5138-3573-4db3-b499-96ef46eca400)
![pol14](https://github.com/user-attachments/assets/6b5358af-1ef5-4439-8ebc-d22757117296)
![pol15](https://github.com/user-attachments/assets/3ee1635a-2893-4ef1-a486-d9684925dac9)
![pol16](https://github.com/user-attachments/assets/1b581756-798a-4246-8ae4-acd18bce9a4c)
![pol17](https://github.com/user-attachments/assets/907c95ba-def1-4b3f-9791-f29bf34ab113)
![pol18](https://github.com/user-attachments/assets/b3c8822d-69bb-492b-b173-cb951abdecb0)
![pol19](https://github.com/user-attachments/assets/9e24895d-aede-4a12-ad9b-14bf970f832a)
![pol20](https://github.com/user-attachments/assets/99051e2a-cb98-4a5b-a63d-0f9e2fbade28)


   * Examples:

     * Windows: Set lock screen timeout, push Wi-Fi config

     * Android: Set PIN length, disable screen capture

     * iOS: Block app store, enforce passcode

     * macOS: Enable FileVault, disable guest access

3. **Create and Assign Security Groups**

   * Go to **Groups \> New group**

     * Example: “Field Devices” (Windows \+ Android)

     * “Admin Devices” (Windows \+ macOS)

   * Assign users/devices to these groups

   * Apply compliance/config profiles to each group
  

---

### **🔹 Phase 4: App Management**

**Goal:** Deploy apps and enforce app protection policies.

1. **Deploy Core Apps**

   * Go to **Apps \> All apps \> Add**

     * **Windows**: Upload Microsoft Edge  
     * **iOS/Android**: Add Outlook or Teams via store link

     * **macOS**: Add Microsoft Defender for Endpoint

2. **Set App Protection Policies**

   * Go to **Apps \> App protection policies \> Create**

     * Platform: iOS/Android

     * Example Rules:

       * Require PIN before app access

       * Block copy/paste from corporate apps

       * Encrypt work data

---

### **🔹 Phase 5: Monitor, Report & Troubleshoot**

**Goal:** Monitor security and resolve issues proactively.

1. **Monitor Compliance**

   * **Intune \> Devices \> Monitor \> Compliance status** (We can view the overall compliance status of our devices and drill down into specific devices or policies to identify and resolve any non-compliance issues. )

   * Review any non-compliant devices (e.g., missing PIN, jailbroken)

2. **Check Sign-in Logs**

   * Go to **Microsoft Entra Admin Center \> Monitoring \> Sign-in logs**

   * Filter by user or failure type

3. **Review Audit Logs**

   * Go to **Microsoft Entra \> Audit logs**

   * Track changes to users, roles, device enrollments, etc.

     

4. **Create Conditional Access (Entra ID)**  
   * Go to **Microsoft Entra \> Protection \> Conditional Access.**  
   * Create a policy to require MFA or block access from non-compliant devices.

