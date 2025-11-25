# 🔐 Azure IAM Security Project
Identity Attacks Simulation Using Microsoft Entra ID (Azure AD)

By: Bhagya Dharennavar

## 📌 Project Overview

This project demonstrates how identity-based attacks are detected using Microsoft Entra ID (Azure Active Directory).
I created a simulated environment with 3 users:

- **AdminUser** – Highly secure admin  
- **AnalystUser** – Normal employee  
- **DevUser** – Misconfigured / weak security user  

Using DevUser, I performed 4 real-world identity attacks:

1. Normal login  
2. Wrong password brute-force attempts  
3. Login from unknown mobile device  
4. Login from a foreign country using VPN (Tokyo, Japan)

All attacks were analyzed using Azure Sign-in Logs, just like real SOC analysts do.

## 🚀 Tools & Platforms Used

| Tool / Website | Purpose | Link |
|----------------|---------|------|
| Microsoft Azure Portal | Identity management, logs, Entra ID | https://portal.azure.com |
| Microsoft Entra Admin Center | User creation, log monitoring | https://entra.microsoft.com |
| ProtonVPN | Foreign country login simulation | https://protonvpn.com |
| Google Chrome / Edge | Browser-based login testing | Installed locally |
| Android Mobile Login | Unknown device attack | Performed manually |

## 🛠️ Entra ID Setup

✔ Created a new Azure AD (Entra ID) tenant  
✔ Added 3 internal users:  
- AdminUser  
- AnalystUser  
- DevUser (weak security)  

✔ Configured each user with:  
- Basic info  
- Authentication settings  
- Sign-in & audit monitoring enabled  

## ⚡ Identity Attack Simulations

### 🔹 Attack 1 – Normal Login (Successful Sign-in)

✔ Behavior  
- DevUser logs in normally  
- No risk detected  
- Single-factor authentication used  
- Same location, same device  

![No MFA Login](<https://github.com/BhagyaDharennavar/Azure-IAM-Security-Project/blob/main/Screenshot/No%20MFA.png>)

---

### 🔹 Attack 2 – Wrong Password Attempts (Brute-force Simulation)

✔ Behavior  
- Azure logs multiple “Failure” sign-ins  
- Error code **50126** (Invalid username/password)  
- IP, location, timestamp captured  

*![Failed Login](<https://github.com/BhagyaDharennavar/Azure-IAM-Security-Project/blob/main/Screenshot/Failed%20login%20azure.png>)


---

### 🔹 Attack 3 – Login from Unknown Device (Mobile Login)

✔ Detection  
- Android Device (Android 10)  
- Chrome Mobile browser  
- New session fingerprint  

![Mobile Login 1](<sandbox:/mnt/data/moblie login.png>)
![Mobile Login 2](<sandbox:/mnt/data/moblie login 1.png>)

---

### 🔹 Attack 4 – Foreign Country Login Using VPN (Tokyo, Japan)

✔ Detection  
- Location: **Tokyo, Japan 🇯🇵**  
- IP Address: **37.19.205.154**  
- Browser fingerprint: Chrome Mobile  
- Single-factor authentication  

![Japan VPN Login](<sandbox:/mnt/data/unknown ip.png>)
![Japan Location](<sandbox:/mnt/data/unknow ip.png>)

---

## 📊 Final Results

| Attack Type | Logged? | Details |
|-------------|---------|---------|
| Normal Login | ✅ Yes | Hubli-Dharwad |
| Wrong Password | ✅ Yes | Error 50126 |
| Unknown Device | ✅ Yes | Android 10 |
| Foreign Country | ✅ Yes | Tokyo, Japan |

---

## 🎯 Key Learning Outcomes

- Identity & Access Management (IAM) fundamentals  
- Cloud authentication flows  
- Azure AD sign-in monitoring  
- SOC investigation techniques  
- Geo-location threat detection  
- Weak identity exploitation  

---

## 📘 Useful Links

- Azure Portal: https://portal.azure.com  
- Entra Admin: https://entra.microsoft.com  
- ProtonVPN: https://protonvpn.com/download  
- Microsoft 365 Developer Program: https://developer.microsoft.com/microsoft-365/dev-program  

---

## 📂 Folder Structure

```
Azure-IAM-Security-Project/
│
├── screenshots/
│   ├── failed-login.png
│   ├── mobile-login.png
│   ├── japan-vpn-login.png
│   ├── normal-login.png
│
├── README.md
└── project-report.pdf (optional)
```

## 🏁 Conclusion

This project successfully demonstrates how Azure Entra ID detects identity threats using:

✔ Sign-in logs  
✔ Device information  
✔ Location analytics  
✔ Authentication details  

A real-world IAM security project suitable for SOC/IAM roles.

## 🙌 Thank You

If you like this project, feel free to ⭐ the repo!
