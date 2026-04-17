# ✈️ Flight Deal Finder (Advanced)

A Python automation system that monitors flight prices and sends real-time alerts when deals are found.

---

## 🚀 Overview

This project integrates multiple APIs to simulate a real-world flight deal tracking system. It retrieves destination data, searches flights, compares prices, and sends notifications via WhatsApp and email.

---

## ✨ Features

* 📊 Fetches destination & user data from Google Sheets (Sheety API)
* 🔍 Searches flights using SerpAPI (Google Flights engine)
* 💰 Identifies cheapest flights across direct and indirect routes
* 🔔 Sends alerts via Twilio (WhatsApp / SMS)
* 📧 Sends email notifications to multiple users
* ⚡ Uses request caching to reduce API usage
* 🔐 Secure API handling via environment variables

---

## 🧠 How It Works

1. Destination data is stored in Google Sheets
2. Customer emails are retrieved from a separate sheet
3. For each destination:

   * Searches direct flights
   * Falls back to indirect flights if needed
   * Finds cheapest option
4. If price is lower than threshold:

   * Updates Google Sheet
   * Sends WhatsApp + email alerts

---

## 🛠 Tech Stack

* Python
* Requests / Requests-Cache
* SerpAPI (Google Flights)
* Sheety API (Google Sheets)
* Twilio API (Notifications)
* SMTP (Email automation)

---

## ⚙️ Setup

### 1. Clone repository

```bash
git clone https://github.com/luck-jp/flight-deal-finder-advanced.git
cd flight-deal-finder-advanced
```

---

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

---

## 🔐 Environment Setup (Required)

This project uses multiple APIs. You will need to create your own API keys.

### Step 1: Create a `.env` file

In the root directory of the project, create a file named:

```
.env
```

---

### Step 2: Add the following variables

```
SERPAPI_API_KEY=your_serpapi_key_here

SHEETY_PRICES_ENDPOINT=your_sheety_prices_endpoint
SHEETY_USERS_ENDPOINT=your_sheety_users_endpoint

TWILIO_SID=your_twilio_sid
TWILIO_AUTH_TOKEN=your_twilio_auth_token
TWILIO_VIRTUAL_NUMBER=your_twilio_number
TWILIO_VERIFIED_NUMBER=your_phone_number
TWILIO_WHATSAPP_NUMBER=+14155238886

EMAIL_PROVIDER_SMTP_ADDRESS=smtp.gmail.com
MY_EMAIL=your_email
MY_EMAIL_PASSWORD=your_app_password
```

---

## 🔑 How to Get API Keys

### 1. SerpAPI (Flight Data)

* Go to: https://serpapi.com/
* Sign up and generate your API key

---

### 2. Sheety (Google Sheets API)

* Go to: https://sheety.co/
* Connect your Google Sheet
* Enable GET and PUT requests
* Copy your API endpoints

---

### 3. Twilio (SMS / WhatsApp)

* Go to: https://console.twilio.com/
* Get:

  * Account SID
  * Auth Token
* Enable WhatsApp Sandbox:

  * Send the join code via WhatsApp

---

### 4. Email (SMTP)

* Use Gmail (recommended)
* Enable 2FA on your account
* Generate an App Password:
  https://myaccount.google.com/apppasswords

---

### 4. Run the project

```bash
python main.py
```

---

## 📸 Example Output

```
Getting direct flights for Paris...
Paris: GBP 120

Lower price flight found!
Sending notification...
```

---

## ⚠️ Limitations

* Flight results depend on SerpAPI and may return no data for certain routes/dates
* Google Flights scraping is less reliable than dedicated flight APIs
* Best results achieved with near-term travel dates

---

## 🔮 Future Improvements

* Switch to more reliable APIs (Amadeus / Kiwi)
* Add GUI (Tkinter or Web dashboard)
* Add user preferences & filters
* Deploy as a scheduled cloud job

---

## 👨‍💻 Author

**Lakshay**
GitHub: https://github.com/luck-jp

---

## ⭐ Support

If you found this useful, consider giving it a star ⭐
