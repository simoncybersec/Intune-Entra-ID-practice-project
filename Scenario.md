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
![1](C:\Users\simon\Desktop\Professional Toolkit\Project for Intune\Project Screenshots\Phase 1.png)

**Note**: *Adding a user in Entra ID (formerly Azure Active Directory) is fundamentally the same as adding a user in the Microsoft 365 admin center, as they both manage the same underlying user store, which is Entra ID. When a user is created in the Microsoft 365 admin center, it's also created in Entra ID, and vice versa.* 

3. **Assign Business Premium licenses**

   * Assign to each user during creation or afterward via “Licenses and apps.”

4. **Assign Roles**  
    In **Microsoft Entra \> Roles and administrators**, assign:

   * **Simon**: Global Administrator

   * **Dina**: AI Administrator

   * **Others**: Standard users

5. **Enable MFA for all users**

   * Go to **Entra ID \> Users \> Per-user MFA**

   * Enforce MFA

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

   * **macOS**:  
      Manual enrollment (or ABM if available).

   * **iPhone & Android**:  
      Install the **Company Portal app** from App Store/Google Play.

3. **Enroll Each Device [https://learn.microsoft.com/en-us/intune/intune-service/user-help/enroll-your-device-in-intune-macos-cp](https://learn.microsoft.com/en-us/intune/intune-service/user-help/enroll-your-device-in-intune-macos-cp)** 

   * **Windows 11**:  
      Go to **Settings \> Accounts \> Access work or school \> Connect**  
      Sign in with a user account. Verify it appears in Intune \> Devices.

   * **macOS**:  
      Open **Company Portal**, sign in with a test user, follow instructions.

   * **iPhone/Android**:  
      Use different users, open **Company Portal**, enroll and approve permissions.

---

### **🔹 Phase 3: Policy Management (Compliance & Configuration)**

**Goal:** Define secure and compliant rules for devices.

1. **Create Device Compliance Policies**

   * Go to **Devices \> Compliance policies \> Create policy**

   * Platform: Windows, iOS, Android, macOS

   * Sample rules:

     * Require password

     * Block rooted/jailbroken

     * Require device encryption

2. **Create Configuration Profiles**

   * Go to **Devices \> Configuration profiles \> Create**

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

