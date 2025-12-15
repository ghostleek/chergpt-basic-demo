# CherGPT-Basic: Custom Chat Assistant

CherGPT-Basic is a simplified, login-free ChatGPT-like interface designed for quick deployment in educational settings. Built with Streamlit and OpenAI, it provides educators with a customizable chat assistant that can be tailored to specific teaching and learning scenarios.

![image](https://github.com/String-sg/chergpt-basic/assets/44336310/7781fef9-7954-4a47-9523-0edb200b48c0)

**Mobile-friendly interface:**

<img src="https://github.com/String-sg/chergpt-basic/assets/44336310/f21a155a-75a2-4ab5-be5f-95c25ca5c2d9" width="200" />

## ✨ Features

- **Custom Instructions**: Set and update custom instructions to guide student interactions with the AI
- **Chat Log Management**: Download and export chat logs as CSV for analysis
- **Learning Analytics**: Generate teaching and learning analytics based on collected chat logs
- **Admin Panel**: Secure admin access with password protection for managing settings
- **App Description Customization**: Customize the app description shown to users
- **Persistent Storage**: Chat history and instructions stored in PostgreSQL database
- **Streaming Responses**: Real-time streaming of AI responses for better user experience

## 🎯 Use Cases

CherGPT-Basic enables a variety of educational use cases:

- **Historical Personas**: Students can interact with historical figures for immersive learning
- **Medical Simulations**: Practice patient interactions with specific medical conditions
- **Language Learning**: Guided scenarios and escape rooms with comprehension checks
- **Custom Tutoring**: Create specialized tutoring assistants for specific subjects
- **Interactive Assessments**: Build conversational assessments with particular tasks as checks for understanding

## 📋 Prerequisites

- Python 3.8 or higher
- OpenAI API key
- PostgreSQL database (NeonDB recommended)
- Streamlit account (for deployment)
- GitHub account (for deployment)

## 🚀 Live Examples

- [Physics CherGPT](https://chergpt-physics-lookang.streamlit.app/) - Deployed from forked repository
- [Physics CPDD CherGPT](https://chergpt-physics-cpdd.streamlit.app/) - Kah How's deployment

## 🛠️ Local Development Setup

### 1. Clone the Repository

```bash
git clone https://github.com/ghostleek/chergpt-basic-demo.git
cd chergpt-basic-demo
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Configure Environment Variables

Create a `.streamlit/secrets.toml` file with the following configuration:

```toml
OPENAI_API_KEY = "your-openai-api-key"
DATABASE_URL = "your-postgresql-connection-string"
ADMIN_PASSWORD = "your-admin-password"
```

### 4. Run Locally

```bash
streamlit run main.py
```

The application will be available at `http://localhost:8501`

## 🌐 Production Deployment

### Overview

There are three main steps for deploying to production:

1. Set up your PostgreSQL database
2. Obtain your OpenAI API key
3. Deploy to Streamlit Cloud

### Step 1: Database Setup (NeonDB)

We recommend using **NeonDB** for your PostgreSQL database. [Get started here](https://console.neon.tech/)

1. **Create an account**: Visit the [NeonDB console](https://console.neon.tech/), log in, and create your account.

   ![image](https://github.com/String-sg/chergpt-basic/assets/44336310/c4921ffc-15ec-48d2-a4ba-8dec02ef66c1)

2. **Create a new project**: Create a free project with Singapore (or your preferred region) as the location. Choose any project and database name you like.

   ![image](https://github.com/String-sg/chergpt-basic/assets/44336310/c5e529e2-74c6-47d8-935e-43b0a911c252)
   
   ![image](https://github.com/String-sg/chergpt-basic/assets/44336310/f5a3f4f3-dfb1-440d-959b-d71c5a6b00e2)

3. **Copy connection string**: Click the copy icon to get your database connection string. This allows you to store data persistently in CherGPT. **Keep this secure** - you'll need it in the next steps.

### Step 2: OpenAI API Key

- If you're unsure how to create an OpenAI API key, see [this guide](https://teachertech.beehiiv.com/p/api-openai).
- **Keep this secure** - you'll need it for deployment.

> **Note**: Plans to migrate to open-source models are in progress.

### Step 3: Deploy to Streamlit Cloud

**Quick Deploy**: [Click here to deploy from this repository](https://share.streamlit.io/)

1. **Create accounts**: You'll be prompted to create a [Streamlit account](https://streamlit.io/) and connect your GitHub account.

   ![image](https://github.com/String-sg/chergpt-basic/assets/44336310/f6db1538-2481-4cd8-95e0-a45a02285768)

2. **Configure deployment**: Select your forked repository and choose a custom domain for your app.

   ![image](https://github.com/String-sg/chergpt-basic/assets/44336310/8574e485-06fb-4b0c-b7d9-48755ce7bc8d)

3. **Set up secrets**: Go to "Advanced settings" and add your configuration to `secrets.toml`:

   ```toml
   OPENAI_API_KEY = "your-openai-api-key"
   DATABASE_URL = "your-neondb-connection-string"
   ADMIN_PASSWORD = "your-chosen-admin-password"
   ```

   ![image](https://github.com/String-sg/chergpt-basic/assets/44336310/114583ab-a36e-4725-8d65-3705393293a3)

4. **Deploy**: Click "Deploy" and wait a few minutes for the app to build and launch.

   ![image](https://github.com/String-sg/chergpt-basic/assets/44336310/6270480b-0e97-4195-815f-5f9b7e2939fd)

## 📁 Project Structure

```
chergpt-basic-demo/
├── app/
│   ├── chatlog/          # Chat log management and analytics
│   ├── db/               # Database connection and utilities
│   └── instructions/     # Custom instructions handling
├── main.py               # Main Streamlit application
├── sidebar.py            # Sidebar configuration and admin panel
├── requirements.txt      # Python dependencies
└── README.md            # This file
```

## 🔐 Security & Authentication

- **Admin Access**: Protected by password authentication (configure in secrets)
- **Database Security**: Connection strings stored as secrets, never committed to repository
- **API Keys**: OpenAI API keys stored securely in Streamlit secrets

For additional security with SSO authentication, check the [Streamlit authentication guide](https://docs.streamlit.io/knowledge-base/deploy/authentication-without-sso).

## 🧪 Testing

Run the test suite:

```bash
pytest app_test.py
```

## 📊 Admin Features

Once authenticated as an admin, you can access:

- **Edit Description**: Customize the app description shown to users
- **Custom Instructions**: Set system prompts to guide the AI's responses
- **Chatlog Management**: Download chat logs and view analytics summaries
- **Database Management**: Drop tables if needed (use with caution)

## 🤝 Contributing

Contributions are welcome! Feel free to:

- Report bugs and issues
- Suggest new features
- Submit pull requests
- Improve documentation

## 📝 License

This project is open-source. Feel free to explore and enhance the functionality of CherGPT-Basic according to your specific needs!

## 🆘 Troubleshooting

### Common Issues

**Database connection errors**: Ensure your `DATABASE_URL` in secrets.toml is correct and the database is accessible.

**OpenAI API errors**: Verify your API key is valid and has sufficient credits.

**Admin login not working**: Check that `ADMIN_PASSWORD` is set correctly in your secrets configuration.

**Local development issues**: Ensure all dependencies are installed with `pip install -r requirements.txt`.

## 📚 Additional Resources

- [Streamlit Documentation](https://docs.streamlit.io/)
- [OpenAI API Reference](https://platform.openai.com/docs/api-reference)
- [NeonDB Documentation](https://neon.tech/docs/introduction)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)

---

**Need help?** Open an issue in the [GitHub repository](https://github.com/ghostleek/chergpt-basic-demo/issues).
