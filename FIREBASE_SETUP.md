# 🔥 Firebase Setup Guide — Invoicebillers

Follow these steps to connect your real Firebase database.

---

## Step 1 — Create a Firebase Project

1. Go to [https://console.firebase.google.com](https://console.firebase.google.com)
2. Click **"Add project"** → Name it `invoicebillers`
3. Disable Google Analytics (optional) → Click **Create project**

---

## Step 2 — Create Firestore Database

1. In your Firebase project, click **"Firestore Database"** in the left menu
2. Click **"Create database"**
3. Choose **"Start in test mode"** (allows read/write for 30 days)
4. Select your region → Click **Enable**

---

## Step 3 — Get Your Firebase Config

1. Click the ⚙️ gear icon → **Project settings**
2. Scroll down to **"Your apps"** → Click **`</>`** (Web app)
3. Register app with name `invoicebillers-web`
4. Copy the `firebaseConfig` object that appears

It looks like this:
```js
const firebaseConfig = {
  apiKey: "AIzaSy...",
  authDomain: "invoicebillers.firebaseapp.com",
  projectId: "invoicebillers",
  storageBucket: "invoicebillers.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abc123"
};
```

---

## Step 4 — Paste Config in All 3 Files

Open each file and find the comment:
```
// 🔧 PASTE YOUR FIREBASE CONFIG BELOW
```

Replace the placeholder values with your real config in **all three files**:
- `index.html`
- `admin.html`
- `dashboard.html`

---

## Step 5 — Set Your Admin Credentials

Open `admin.html` and find:
```js
const ADMIN_EMAIL = "admin@invoicebillers.com";
const ADMIN_PASS  = "Admin@1234";
```

Change these to your own private email and password.

> ⚠️ Keep this secret — this is how you log into your admin panel.

---

## Step 6 — Set Firestore Security Rules (Optional but recommended)

In Firebase Console → Firestore → **Rules**, paste:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /requests/{doc} {
      allow read, write: if true; // tighten later
    }
    match /invoices/{doc} {
      allow read, write: if true;
    }
  }
}
```

---

## Step 7 — Upload All Files to GitHub

Upload these 4 files to your GitHub repo:
- `index.html` — Main landing page
- `admin.html` — Admin panel (keep URL private)
- `dashboard.html` — Customer billing dashboard
- `FIREBASE_SETUP.md` — This guide (optional)

---

## How the System Works

```
Customer fills Sign Up form on index.html
        ↓
Request saved to Firebase (status: "pending")
        ↓
Admin logs into admin.html → Reviews request
        ↓
Admin clicks ✅ Approve → status becomes "approved"
        ↓
Customer can now Sign In on index.html
        ↓
Customer lands on dashboard.html → Creates invoices
```

---

## Admin Panel URL

Access your admin panel at:
```
https://krishikasj-invoicewhizz.github.io/invoicebillers/admin.html
```

Keep this URL private — only share with yourself!
