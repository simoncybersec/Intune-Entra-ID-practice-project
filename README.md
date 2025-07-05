# 🎯 Microsoft Intune & Entra ID Practice Project

## 📖 Project Overview

This project simulates the role of an IT administrator managing users, devices, and security policies in a small organization using **Microsoft Intune**, **Microsoft Entra ID (Azure AD)**, and a **Microsoft 365 Business Premium trial**. The goal was to practice real-world IT admin tasks such as device enrollment, compliance management, app deployment, Conditional Access, and troubleshooting.

---

## 🏢 Scenario

I volunteered as an IT admin for a small organization that uses various devices to access company resources. My goal was to:
- Securely enroll and manage personal and company-owned devices.
- Protect user accounts and data using Multi-Factor Authentication (MFA) and Conditional Access.
- Deploy and configure essential apps.
- Ensure device compliance with organizational security policies.

### Environment Setup:
- **Microsoft 365 Business Premium Trial**
- Devices used:
  - Windows 11 PC
  - macOS
  - iPhone
  - Android devices

---

## 🔧 Phases of the Project

### Phase 1: Initial Tenant Setup
- Created a Microsoft 365 tenant using a Business Premium trial.
- Created multiple test user accounts.
- Assigned appropriate roles and licenses.
- Enabled MFA for all users via Microsoft Entra ID.

### Phase 2: Device Enrollment
- Enrolled Windows, macOS, iOS, and Android devices into Intune.
- Used automatic enrollment for Windows and manual enrollment via the Company Portal app for other devices.

### Phase 3: Policy Management
- Created compliance policies for Windows, macOS, iOS, and Android:
  - Enforced passwords, encryption, and security baselines.
- Configured device profiles for:
  - Wi-Fi, passcode policies, and feature restrictions.
- Created and assigned dynamic security groups.

### Phase 4: App Management
- Deployed Microsoft Edge to Windows.
- Pushed Outlook and Microsoft Teams to iOS/Android.
- Applied App Protection Policies to secure mobile apps.

### Phase 5: Conditional Access & Monitoring
- Configured Conditional Access to require MFA for non-US logins.
- Blocked access for non-compliant devices.
- Monitored sign-in logs, compliance status, and device health.
- Performed troubleshooting for MFA failures and non-compliant devices.

---

## 🔍 Troubleshooting Scenarios Practiced
- Fixing devices marked as non-compliant due to missing encryption or passcode.
- Resolving MFA issues by resetting authentication methods.
- Retiring devices from Intune without factory resetting personal devices.
- Reviewing sign-in logs for unauthorized access attempts.

---

## 🚀 Key Learnings
- Hands-on experience with Intune's device lifecycle management.
- Practical application of Conditional Access policies.
- Understanding of compliance policy creation and enforcement.
- Real-world troubleshooting of enrollment and MFA problems.

---

## 📂 Repository Contents
- `SCENARIO.md`: This scenario description.

---

## 🛡️ Tools Used
- Microsoft Intune Admin Center
- Microsoft Entra Admin Center
- Microsoft 365 Admin Center
- Company Portal (iOS/Android/macOS)
- Windows Settings (Accounts > Access work or school)

---

## 📅 Status
✅ Completed and tested during my Microsoft 365 Business Premium trial period.

---

