# SPIMAS - Smart Public Infrastructure Monitoring & Accountability System

## 📋 Overview

**SPIMAS** is a web-based government project management system designed to enhance transparency and accountability in public infrastructure projects across Rwanda. The system enables citizens to report infrastructure issues, engineers to validate reports, and contractors to manage work orders efficiently.

**Tagline:** *Every Rwandan citizen deserves to know where public funds go.*

---

## 🎯 System Goals

- **Transparency** – Making budgets and project progress visible to all citizens
- **Accountability** – Holding officials and contractors responsible for project delivery
- **Real-time Monitoring** – Live tracking of infrastructure projects and issue resolutions

---

## 🏗️ Project Structure

```
SPIMAS_PROJECT-FOR-GOVT11/
├── index.html                    # Home page
├── citizen.html                  # Citizen Portal for reporting issues
├── engineeringdashboard.html     # Engineer Dashboard for report validation
├── contractorportal.html         # Contractor Portal for work order management
├── css/
│   └── spamis_styling.css       # Main stylesheet
└── README.md                     # This file
```

---

## 👥 User Roles & Features

### 1. **Citizens**
- **Access:** Citizen Portal (`citizen.html`)
- **Features:**
  - User login with name, national ID, email, and password
  - Report infrastructure issues (potholes, street lights, water pipes, etc.)
  - Specify issue severity (1-5 scale)
  - View active government projects and their status
  - Track reports submitted
  - View personalized welcome greeting when logged in

### 2. **District Engineers**
- **Access:** Engineer Dashboard (`engineeringdashboard.html`)
- **Features:**
  - View all citizen-submitted reports
  - Validate reports to create work orders
  - Reject invalid reports
  - Monitor report statistics (pending, validated, rejected)
  - Automatically create work orders for validated reports
  - Assign contractors to tasks

### 3. **Contractors**
- **Access:** Contractor Portal (`contractorportal.html`)
- **Features:**
  - View assigned work orders
  - Update work order status (Assigned → Started → In Progress → Completed)
  - Submit completion evidence with photos and notes
  - Track work order statistics
  - Manage multiple projects simultaneously

---

## 🔑 Key Features

### Citizen Portal
- **Login System** – Name, National ID, Email, Password authentication
- **Report Submission** – Submit infrastructure problems with:
  - Issue type/category
  - Location (District)
  - Severity level (1-5)
  - Detailed description
- **Project Dashboard** – View active government projects, budgets, and status
- **Session Persistence** – Login information stored in browser localStorage

### Engineer Dashboard
- **Report Inbox** – View all submitted citizen reports
- **Validation Workflow** – Approve/reject reports with one-click actions
- **Auto Work Order Generation** – Create contractor work orders upon validation
- **Statistics Panel** – Track total, pending, validated, and rejected reports
- **Severity Labeling** – Color-coded severity indicators

### Contractor Portal
- **Work Order Management** – View and update assigned tasks
- **Status Tracking** – Progress through work stages (Assigned → Started → In Progress → Completed)
- **Evidence Submission** – Upload photos and notes upon completion
- **Performance Metrics** – View statistics on completed vs. active work orders
- **Quick Actions** – One-click status transitions

---

## 💾 Data Storage

The system uses **Browser LocalStorage** for data persistence:
- `spimas_user_name` – Logged-in user's name
- `spimas_user_email` – Logged-in user's email
- `spimas_reports` – Array of citizen-submitted reports
- `spimas_work_orders` – Array of contractor work orders

**Note:** Data is stored locally in the browser and will be cleared if browser cache is cleared.

---

## 📊 Data Flow

```
Citizens Submit Reports
         ↓
  [Engineer Reviews]
         ↓
  [Validates/Rejects]
         ↓
[Work Order Created]
         ↓
Contractors Assigned
         ↓
[Complete Work]
         ↓
Evidence Submitted
```

---

## 🚀 Getting Started

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- No backend server required (client-side only)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/MUHIRWACODER/SPIMAS_PROJECT-FOR-GOVT11.git
   cd SPIMAS_PROJECT-FOR-GOVT11
   ```

2. **Open in browser:**
   - Simply open `index.html` in your web browser
   - Or use a local server:
     ```bash
     python -m http.server 8000
     ```
   - Then navigate to `http://localhost:8000`

### Quick Tour

1. **Home Page** (`index.html`) – Start here to login or access portals
2. **Citizen Portal** (`citizen.html`) – Report issues or view projects
3. **Engineer Dashboard** (`engineeringdashboard.html`) – Manage reports
4. **Contractor Portal** (`contractorportal.html`) – Manage work orders

---

## 🔍 Sample Data

The system comes pre-populated with sample data:

### Sample Reports
- Pothole on main road (Nyarugenge, Severity 5)
- Flickering street light (Gasabo, Severity 2)

### Sample Work Orders
- Pothole Repair (WO-501, Assigned)
- Street Light Fix (WO-502, Started)
- Water Pipe Repair (WO-503, In Progress)

### Sample Projects
- Kigali Ring Road – 12.4B RWF (On Track)
- Bugesera Water – 5.8B RWF (Delayed)

---

## 🎨 Styling

The project uses a centralized stylesheet:
- **Location:** `css/spamis_styling.css`
- **Features:**
  - Color-coded status indicators
  - Responsive table layouts
  - Professional government portal theme
  - Status badges (Pending, Validated, Rejected, Completed)

---

## 🔐 Security Notes

⚠️ **Current Implementation:**
- This is a **proof-of-concept** system using browser localStorage
- **Not suitable for production** without proper backend security
- Passwords are not encrypted
- Session data is visible in browser storage

🔒 **For Production Deployment:**
- Implement server-side authentication (OAuth, JWT)
- Use encrypted database storage
- Add role-based access control (RBAC)
- Implement audit logging
- Use HTTPS for all communications
- Add input validation and sanitization
- Implement file upload security for evidence photos

---

## 📱 Supported Browsers

- ✅ Google Chrome 90+
- ✅ Mozilla Firefox 88+
- ✅ Safari 14+
- ✅ Microsoft Edge 90+

---

## 🌐 Contact & Support

- **Email:** info@spimas.gov.rw
- **Hotline:** +250 791980831
- **Partners:** Government of Rwanda in partnership with Jules Co.

---

## 📄 License

This project is developed for the Government of Rwanda. All rights reserved.

---

## 🤝 Contributing

To contribute to this project:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -m 'Add YourFeature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

---

## 🐛 Known Limitations

1. **No Backend** – Uses only client-side storage (localStorage)
2. **No Real Authentication** – Basic form validation only
3. **Single Device** – Data not synced across devices
4. **No File Storage** – Evidence photos cannot be truly uploaded
5. **No Real-time Updates** – Manual page refresh required for updates

---

## 🔮 Future Enhancements

- [ ] Backend database integration (Firebase, MongoDB, PostgreSQL)
- [ ] Real authentication system with role-based access
- [ ] Mobile app version (React Native, Flutter)
- [ ] Real-time notifications and SMS alerts
- [ ] Geographic mapping of infrastructure projects
- [ ] Analytics and reporting dashboard
- [ ] Multi-language support (French, Kinyarwanda)
- [ ] File upload and storage for evidence photos
- [ ] Email notifications for status updates
- [ ] Integration with government payment systems

---

## 📝 Project Timeline

- **May 2026** – System launched for pilot testing
- **Ongoing** – Collecting feedback and refining features

---

## ✨ Credits

**Developer:** MUHIRWACODER  
**Project Name:** SPIMAS (Smart Public Infrastructure Monitoring & Accountability System)  
**Year:** 2026

---

**Last Updated:** June 29, 2026

For more information, visit the MINECOFIN website: [www.minecofin.gov.rw](https://www.minecofin.gov.rw)
