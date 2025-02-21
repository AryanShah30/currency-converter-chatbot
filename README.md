# ExchangeEase: Telegram Currency Conversion Chatbot

## Overview

ExchangeEase is a sophisticated currency conversion chatbot deployed on Telegram. It leverages Google Dialogflow for natural language processing, a Flask-based API for backend logic, and ngrok for secure tunneling during development. This solution provides real-time currency conversion capabilities directly within Telegram, ensuring seamless user experience and efficient performance.

## Features

- Real-time currency conversion via Telegram
- Natural language processing for user queries
- Support for multiple currencies
- Secure API communication
- Easy-to-use Telegram interface

## Architecture

The project consists of four main components:

1. **Telegram Bot**: The user interface for interacting with the chatbot.
2. **Dialogflow Agent**: Handles natural language understanding and conversation flow.
3. **Flask API**: Processes conversion requests and interacts with external currency exchange APIs.
4. **ngrok**: Provides secure tunneling to expose the local Flask server to the internet during development.

## Prerequisites

- Python 3.7+
- Google Cloud account with Dialogflow API enabled
- Telegram Bot Token
- ngrok account (for development)
- API key for a currency exchange rate service (e.g., ExchangeRate-API)

## Installation

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/ExchangeEase.git
   cd ExchangeEase
   ```

2. Set up a virtual environment:
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

4. Set up environment variables:
   Create a `.env` file in the project root and add:
   ```
   DIALOGFLOW_PROJECT_ID=your_project_id
   EXCHANGE_RATE_API_KEY=your_api_key
   TELEGRAM_BOT_TOKEN=your_telegram_bot_token
   ```

## Usage

1. Start the Flask server:
   ```
   python app.py
   ```

2. For local development, in a separate terminal, start ngrok:
   ```
   ngrok http 5000
   ```

3. Update the webhook URL in your Dialogflow agent settings with the ngrok HTTPS URL.

4. Open Telegram and start a conversation with your bot.

## API Reference

### POST /webhook

Handles incoming webhook requests from Dialogflow.

**Request Body:**
```json
{
  "queryResult": {
    "parameters": {
      "amount": 100,
      "source_currency": "USD",
      "target_currency": "EUR"
    }
  }
}
```

**Response:**
```json
{
  "fulfillmentText": "100 USD is equivalent to 85.23 EUR"
}
```

## Telegram Integration

To use the ExchangeEase bot on Telegram:

1. Search for your bot's username in Telegram.
2. Start a conversation by clicking the "Start" button.
3. Type your currency conversion query, e.g., "Convert 100 USD to EUR".
4. The bot will respond with the converted amount.

## Deployment

For production deployment:

1. Set up a cloud server (e.g., Google Cloud, AWS, DigitalOcean).
2. Deploy the Flask application using a production WSGI server like Gunicorn.
3. Set up HTTPS using a reverse proxy like Nginx.
4. Update the Dialogflow webhook URL to your production server's URL.
5. Ensure your Telegram bot token is securely stored and accessed in the production environment.

## Contributing
Contributions to enhance the analysis or extend the project are welcome. Please feel free to fork the repository and submit pull requests.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact
For inquiries, suggestions, or feedback, please reach out to: [AryanShah30](https://github.com/AryanShah30)
