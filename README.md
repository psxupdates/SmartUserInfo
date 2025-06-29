# SmartUserInfo 🌟

SmartUserInfo is a powerful Telegram Info API built with FastAPI and Pyrogram, designed to retrieve detailed information about Telegram users, bots, channels, and groups. This API provides insights such as account age estimation, data center locations, premium status, and real-time status tracking. 💥

**Project URL**: [github.com/TheSmartDevs/SmartUserInfo](https://github.com/TheSmartDevs/SmartUserInfo) ✅

**Updates Channel**: [t.me/TheSmartDev](https://t.me/TheSmartDev) 🌟

**Developer**: [@ISmartCoder](https://t.me/ISmartCoder) 💥

---

## Features ✅

- **User & Bot Information** 🌟: Retrieve details like user ID, username, first/last name, premium status, verification status, and account flags (e.g., scam or fake).
- **Channel & Group Details** 💥: Fetch information about Telegram channels, groups, and supergroups, including member count, description, and join links.
- **Account Age Estimation** ✅: Estimate the account creation date based on user ID with a custom algorithm.
- **Data Center Location** ❄️: Identify the Telegram data center location (e.g., Miami, Amsterdam, Singapore) for users and chats.
- **Real-time Status Tracking** 🌟: Get the current status of users (e.g., online, offline, recently online).
- **FastAPI Integration** 💥: Provides a robust, scalable API with endpoints for health checks, entity information, and interactive documentation.
- **Pyrogram Backend** ✅: Leverages Pyrogram for reliable Telegram API interactions.
- **Error Handling** ❄️: Comprehensive error handling for invalid usernames, channels, or other issues.
- **Deployment Ready** 🌟: Easy setup instructions for Render, Heroku, or VPS.

---

## API Endpoints 💥

| Endpoint         | Description                                | Parameters                     |
|------------------|--------------------------------------------|--------------------------------|
| `/`              | Serves the status dashboard (HTML) 🌟      | None                           |
| `/info`          | Retrieves Telegram entity information ✅    | `username` (query parameter)   |
| `/health`        | API health check and detailed information ❄️ | None                           |
| `/docs`          | Interactive Swagger UI documentation 🌟     | None                           |
| `/redoc`         | Alternative ReDoc API documentation ✅      | None                           |

### Response Format 🌟

The API returns JSON responses with a consistent structure:

- **Success Response** ✅:
  ```json
  {
    "success": true,
    "type": "user|bot|group|supergroup|channel",
    "id": "<entity_id>",
    "first_name": "<first_name>", // For users/bots
    "last_name": "<last_name>",   // For users/bots
    "username": "<username>",
    "dc_id": <data_center_id>,
    "dc_location": "<location>",
    "is_premium": <boolean>,      // For users/bots
    "is_verified": <boolean>,     // For users/bots
    "is_bot": <boolean>,          // For users/bots
    "flags": "Clean|Scam|Fake",   // For users/bots
    "status": "<status>",         // For users/bots
    "account_created": "<date>",  // For users/bots
    "account_age": "<age>",       // For users/bots
    "members_count": <number>,    // For groups/channels
    "description": "<description>", // For groups/channels
    "api_dev": "@ISmartCoder",
    "api_updates": "https://t.me/TheSmartDev",
    "links": {
      "android": "<tg_link>",
      "ios": "<tg_link>",
      "permanent": "<tg_link>",
      "join": "<tg_link>"         // For groups/channels
    }
  }
  ```

- **Error Response** ❌:
  ```json
  {
    "success": false,
    "error": "<error_message>"
  }
  ```

---

## Setup Instructions ❄️

### Prerequisites 🌟

- Python 3.8+
- Telegram API credentials (`API_ID`, `API_HASH`, `BOT_TOKEN`) ✅
  - Obtain these from [my.telegram.org](https://my.telegram.org) and create a bot via [@BotFather](https://t.me/BotFather).
- Git
- A deployment platform (Render, Heroku, or VPS) 💥

### Local Setup ✅

1. **Clone the Repository** 🌟:
   ```bash
   git clone https://github.com/TheSmartDevs/SmartUserInfo.git
   cd SmartUserInfo
   ```

2. **Install Dependencies** 💥:
   ```bash
   pip install -r requirements.txt
   ```
   Ensure `requirements.txt` includes:
   ```
   fastapi
   uvicorn
   pyrogram
   python-dateutil
   ```

3. **Configure Environment Variables** ✅:
   Create a `config.py` file in the project root with the following:
   ```python
   API_ID = "your_api_id"
   API_HASH = "your_api_hash"
   BOT_TOKEN = "your_bot_token"
   ```

4. **Create Status Page** ❄️:
   Create a `status.html` file in the project root for the `/` endpoint. Example:
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>SmartUserInfo API 🌟</title>
   </head>
   <body>
       <h1>SmartUserInfo API 💥</h1>
       <p>API is running! Check <a href="/docs">API Docs</a> for details. ✅</p>
       <p>Developed by <a href="https://t.me/ISmartCoder">@ISmartCoder</a> 🌟</p>
       <p>Updates: <a href="https://t.me/TheSmartDev">t.me/TheSmartDev</a> 💥</p>
   </body>
   </html>
   ```

5. **Run the Application** ✅:
   ```bash
   python app.py
   ```
   The API will be available at `http://localhost:5000`.

---

### Deployment 💥

#### 1. Deploy on Render 🌟

1. **Create a Render Account** ✅:
   Sign up at [render.com](https://render.com) and create a new Web Service.

2. **Connect GitHub Repository** ❄️:
   Link your GitHub repository (`github.com/TheSmartDevs/SmartUserInfo`) to Render.

3. **Configure Build Settings** ✅:
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `python app.py`
   - **Environment Variables**:
     - `API_ID`: Your Telegram API ID
     - `API_HASH`: Your Telegram API Hash
     - `BOT_TOKEN`: Your Telegram Bot Token
     - `PORT`: `5000` (default)

4. **Add Status Page** 🌟:
   Ensure `status.html` is included in your repository.

5. **Deploy** 💥:
   Trigger the deployment from Render’s dashboard. The API will be accessible at the provided Render URL.

#### 2. Deploy on Heroku ✅

[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/TheSmartDevs/SmartUserInfo)

1. **Create a Heroku Account** 🌟:
   Sign up at [heroku.com](https://heroku.com).

2. **Deploy via Button** 💥:
   Click the "Deploy to Heroku" button above, or manually deploy:
   - Clone the repository and push to Heroku:
     ```bash
     heroku create
     git push heroku main
     ```

3. **Configure Environment Variables** ✅:
   In the Heroku dashboard, add:
   - `API_ID`
   - `API_HASH`
   - `BOT_TOKEN`

4. **Add Buildpacks** ❄️:
   Add the Python buildpack in the Heroku dashboard or via:
   ```bash
   heroku buildpacks:set heroku/python
   ```

5. **Add Status Page** 🌟:
   Ensure `status.html` is in the repository.

6. **Scale Dynos** ✅:
   ```bash
   heroku ps:scale web=1
   ```

7. **Access the API** 💥:
   The API will be available at `https://your-app-name.herokuapp.com`.

#### 3. Deploy on VPS ❄️

1. **Set Up VPS** 🌟:
   Use a provider like DigitalOcean, AWS, or Linode. Install Ubuntu 20.04+.

2. **Install Dependencies** ✅:
   ```bash
   sudo apt update
   sudo apt install python3 python3-pip git
   ```

3. **Clone Repository** 💥:
   ```bash
   git clone https://github.com/TheSmartDevs/SmartUserInfo.git
   cd SmartUserInfo
   pip3 install -r requirements.txt
   ```

4. **Configure Environment Variables** ✅:
   Create a `config.py` file or export variables:
   ```bash
   export API_ID="your_api_id"
   export API_HASH="your_api_hash"
   export BOT_TOKEN="your_bot_token"
   ```

5. **Add Status Page** 🌟:
   Create `status.html` as described in the local setup.

6. **Run with Uvicorn** 💥:
   ```bash
   uvicorn app:app --host 0.0.0.0 --port 5000
   ```

7. **Set Up Reverse Proxy (Optional)** ❄️:
   Use Nginx to expose the API:
   ```bash
   sudo apt install nginx
   sudo nano /etc/nginx/sites-available/smartuser
   ```
   Add:
   ```nginx
   server {
       listen 80;
       server_name your_domain_or_ip;
       location / {
           proxy_pass http://localhost:5000;
           proxy_set_header Host $host;
           proxy_set_header X-Real-IP $remote_addr;
       }
   }
   ```
   Enable and restart Nginx:
   ```bash
   sudo ln -s /etc/nginx/sites-available/smartuser /etc/nginx/sites-enabled/
   sudo systemctl restart nginx
   ```

8. **Run in Background** ✅:
   Use `screen` or `pm2` to keep the app running:
   ```bash
   pip3 install pm2
   pm2 start "uvicorn app:app --host 0.0.0.0 --port 5000" --name smartuser
   ```

---

## API Documentation 🌟

- **Interactive Docs** ✅: Access at `/docs` (Swagger UI) or `/redoc` (ReDoc).
- **Example Request** 💥:
  ```bash
  curl -X GET "http://your-api-url/info?username=ISmartCoder"
  ```

- **Example Response (User)** ✅:
  ```json
  {
    "success": true,
    "type": "user",
    "id": 123456789,
    "first_name": "Smart",
    "last_name": "Coder",
    "username": "ISmartCoder",
    "dc_id": 4,
    "dc_location": "STO, Stockholm, Sweden, SE",
    "is_premium": false,
    "is_verified": false,
    "is_bot": false,
    "flags": "Clean",
    "status": "Online",
    "account_created": "August 13, 2020",
    "account_age": "4 years, 10 months, 16 days",
    "api_dev": "@ISmartCoder",
    "api_updates": "https://t.me/TheSmartDev",
    "links": {
      "android": "tg://openmessage?user_id=123456789",
      "ios": "tg://user?id=123456789",
      "permanent": "tg://user?id=123456789"
    }
  }
  ```

- **Example Response (Channel)** 🌟:
  ```json
  {
    "success": true,
    "type": "channel",
    "id": -100123456789,
    "title": "TheSmartDev",
    "username": "TheSmartDev",
    "dc_id": 2,
    "dc_location": "AMS, Amsterdam, Netherlands, NL",
    "members_count": 1000,
    "description": "Updates for SmartUserInfo API",
    "api_dev": "@ISmartCoder",
    "api_updates": "https://t.me/TheSmartDev",
    "links": {
      "join": "t.me/TheSmartDev",
      "permanent": "t.me/TheSmartDev"
    }
  }
  ```

---

## Contributing 💥

Contributions are welcome! Please:
1. Fork the repository. 🌟
2. Create a new branch (`git checkout -b feature/your-feature`). ✅
3. Commit your changes (`git commit -m 'Add your feature'`). ❄️
4. Push to the branch (`git push origin feature/your-feature`). 💥
5. Open a pull request. ✅

---

## License ✅

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details. 🌟

---

## Support ❄️

For support, join our updates channel: [t.me/TheSmartDev](https://t.me/TheSmartDev) or contact [@ISmartCoder](https://t.me/ISmartCoder). 💥

