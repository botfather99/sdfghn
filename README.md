# BomBX-CLI 📱💥

A powerful SMS, Call & WhatsApp bombing tool for educational and testing purposes. 

## ⚠️ Disclaimer
This tool is for educational purposes only. Use it responsibly and only on phone numbers you own or have explicit permission to test. The developer is not responsible for any misuse of this tool.

📍 **Note: This script only works for Indian phone numbers.**

## ✨ Features

- **SMS Bombing**: Send multiple SMS messages through various APIs
- **Call Bombing**: Make multiple calls through different APIs
- **WhatsApp Support**: Send multiple WhatsApp messages through various APIs
- **Multi Mode**: Combine SMS, Call & WhatsApp bombing simultaneously
- **Configurable APIs**: Easy to add/remove APIs via JSON configuration
- **Rate Limiting**: Built-in sleep functionality to respect API limits
- **Detailed Logging**: Comprehensive logging with timestamps
- **Error Handling**: Robust error handling and debugging features

## Logging System
- All responses are logged to `BomBX-Logs.txt`
- Timestamps included for each request
- Success/failure status tracking
- Detailed error information
- Debug mode is enabled by default API responses are printed to the console and logged to file

## Smart Request Management
- Automatic rate limiting based on API configuration
- Prevents duplicate consecutive requests
- Handles both GET and POST methods
- JSON payload formatting for POST requests


## 🛠️ Installation

1. Clone the repository:
```bash
git clone https://github.com/BetterCallShiv/BomBX-CLI.git
cd BomBX-CLI
```

2. Install required dependencies:
```bash
pip install requests
```

## 🚀 Usage

1. Run the script:
```bash
python3 main.py
```

2. Enter the target phone number when prompted

3. Choose your bombing mode:
   - **1**: SMS only
   - **2**: Call only
   - **3**: WhatsApp only
   - **4**: SMS, Call & WhatsApp (Multi mode)

4. The tool will start sending requests based on your configuration

## ⚙️ Configuration (For Developers)

Create an `api_config.json` file in the project root with the following structure:

```json
{
  "BomBX_API": {
    "Example1": {
      "type": "sms",
      "method": "GET",
      "url": "https://api.example.com/send-otp?phone={phone}",
      "headers": {
        "User-Agent": "Mozilla/5.0..."
      },
      "sleep": 30
    },
    "Example2": {
      "type": "sms",
      "method": "POST",
      "url": "https://api.example.com/otp/send",
      "headers": {
        "Content-Type": "application/json"
      },
      "data": {
        "phone": "{phone}",
        "country_code": "+91"
      },
      "cookies": {
        "session_id": "abc123"
      },
      "sleep": 60
    },
    "Example3": {
      "type": "whatsapp",
      "method": "POST",
      "url": "https://api.example.com/wa/send",
      "headers": {
        "Content-Type": "application/json"
      },
      "data": "{\"phone\":\"{phone}\",\"channel\":\"whatsapp\"}",
      "sleep": 30
    },
    "Example4": {
      "type": "call",
      "method": "POST",
      "url": "https://api.example.com/call/trigger",
      "headers": {
        "Content-Type": "application/json"
      },
      "data": {
        "mobile": "{phone}"
      },
      "sleep": 120
    }
  }
}
```

## Configuration Parameters:
- **type**: API type (`sms`, `call` or `whatsapp`)
- **url**: API endpoint URL (use `{phone}` placeholder)
- **method**: HTTP method (`GET` or `POST`)
- **sleep**: Delay between requests in seconds
- **headers**: HTTP headers (optional)
- **data**: Request payload (optional) — supports JSON object (`{}`), JSON string (`"{...}"`) or form-encoded string (`"key={phone}"`)
- **cookies**: Cookies as a key-value object or semicolon-separated string (optional)

> **Note:** The `{phone}` placeholder is supported in `url`, `headers`, `data` and `cookies` it gets replaced with the target phone number at runtime.


## 📜 License

This project is for educational purposes only. Please use responsibly and in compliance with local laws and regulations.

**⚠️ Remember**: Always use this tool ethically and responsibly. Only test on numbers you own or have explicit permission to use.

## 👨‍💻 Author

**Shivam Raj** ([@BetterCallShiv](https://github.com/BetterCallShiv))
- Email: [bettercallshiv@gmail.com](mailto:bettercallshiv@gmail.com)
- GitHub: [github.com/BetterCallShiv](https://github.com/BetterCallShiv)
