# Deployment Guide

## Option 1: Heroku (Recommended for Flask apps)

### 1. Create a Heroku account

- Go to [heroku.com](https://heroku.com) and sign up

### 2. Install Heroku CLI

- Download from [devcenter.heroku.com](https://devcenter.heroku.com/articles/heroku-cli)

### 3. Deploy to Heroku

```bash
# Login to Heroku
heroku login

# Create a new Heroku app
heroku create your-excel-comparison-tool

# Set environment variables
heroku config:set FLASK_ENV=production

# Deploy
git add .
git commit -m "Initial deployment"
git push heroku main

# Open the app
heroku open
```

## Option 2: Railway

### 1. Create a Railway account

- Go to [railway.app](https://railway.app) and sign up

### 2. Deploy

- Connect your GitHub repository
- Railway will automatically detect the Flask app
- Deploy with one click

## Option 3: Render

### 1. Create a Render account

- Go to [render.com](https://render.com) and sign up

### 2. Deploy

- Connect your GitHub repository
- Create a new Web Service
- Use these settings:
  - Build Command: `pip install -r requirements.txt`
  - Start Command: `python app.py`

## Option 4: PythonAnywhere

### 1. Create a PythonAnywhere account

- Go to [pythonanywhere.com](https://pythonanywhere.com) and sign up

### 2. Deploy

- Upload your files via the web interface
- Create a new web app
- Configure the WSGI file

## Environment Variables

Make sure to set these in your hosting platform:

- `FLASK_ENV=production`
- `PORT` (usually set automatically by the platform)

## File Structure

Your project should have:

```
├── app.py
├── requirements.txt
├── Procfile
├── runtime.txt
├── templates/
│   └── index.html
├── uploads/ (created automatically)
└── README.md
```

## Notes

- The app will automatically create the `uploads/` directory
- Files are cleaned up after processing
- Maximum file size is 16MB
- The app runs on the port specified by the hosting platform
