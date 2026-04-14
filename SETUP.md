# Clubhouse Clone Setup Guide

This guide will help you set up and run the Clubhouse clone application with Stream.io integration.

## Prerequisites

- Node.js (version 16 or higher)
- npm (comes with Node.js)
- Stream.io account (you mentioned you already have one)

## Stream.io Configuration

### 1. Get your Stream.io credentials

1. Go to [Stream.io Dashboard](https://dashboard.getstream.io/)
2. Sign in to your account
3. Select your app or create a new one
4. From the dashboard, you'll need:
   - **API Key** (safe to share, used by both client and server)
   - **Secret** (keep secure, only used by server)

### 2. Configure Environment Variables

#### Server Configuration
Edit the file `server/.env` and replace the placeholder values:

```bash
# Stream.io Configuration
STREAM_API_KEY=your_actual_api_key_here
STREAM_SECRET=your_actual_secret_here

# Server Configuration
PORT=3001
```

#### Client Configuration
Edit the file `client/.env` and replace the placeholder values:

```bash
# Stream.io Configuration for Client
VITE_API_KEY=your_actual_api_key_here
```

**Note**: Use the same API Key for both server and client.

## Running the Application

### Option 1: Manual Startup

#### Start the Server (Terminal 1)
```bash
cd server
npm run dev
```

#### Start the Client (Terminal 2)
```bash
cd client
npm run dev
```

### Option 2: Using the Provided Script

Run the start script from the root directory:
```bash
npm start
```

## Accessing the Application

- **Client (Frontend)**: http://localhost:5173
- **Server (Backend)**: http://localhost:3001

## Troubleshooting

### Common Issues

1. **"STREAM_API_KEY and STREAM_SECRET environment variables are required" error**
   - Make sure you've filled in the actual values in both `.env` files
   - Restart the server after updating the `.env` file

2. **Client build issues with unused imports**
   - This is expected during development
   - The development server (`npm run dev`) will work fine
   - You can ignore these warnings for now

3. **Port conflicts**
   - If port 3001 is taken, update the `PORT` value in `server/.env`
   - If port 5173 is taken, Vite will automatically suggest another port

### Verification Steps

1. Check that the server starts without errors
2. Check that the client loads in your browser
3. Try creating a user account
4. Test joining/creating rooms

## Project Structure

```
clubhouse-clone/
├── client/           # React frontend (Vite + TypeScript)
├── server/           # Node.js backend (Express + TypeScript)
├── client/.env       # Client environment variables
├── server/.env       # Server environment variables
└── SETUP.md         # This file
```

## Next Steps

1. Fill in your actual Stream.io credentials in both `.env` files
2. Run both the server and client
3. Open http://localhost:5173 in your browser
4. Test the application by creating a user and joining rooms

## Need Help?

If you encounter any issues, check:
1. That all dependencies are installed (`npm install` in both client and server directories)
2. That your Stream.io credentials are correct
3. That both the server and client are running
4. Browser console for any client-side errors
5. Terminal/console for any server-side errors
