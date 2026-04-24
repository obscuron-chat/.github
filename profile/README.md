<div align="center">
  <table border="1">
    <tr>
      <td align="center" style="padding: 20px;">
        <h3>📢 Domain & Email Migration Notice</h3>
        <p>From <b>May 14 th, 2026</b>, Obscuron will transition to new domains as <code>obscuron.chat</code> will not be renewed:</p>
        <p>🌐 <b>Website:</b> <a href="https://obscuron.faizath.com">obscuron.faizath.com</a> (formerly <i>obscuron.chat</i>)<br>
        ⚙️ <b>API:</b> <a href="https://obscuron-api.faizath.com">obscuron-api.faizath.com</a> (formerly <i>api.obscuron.chat</i>)<br>
        📧 <b>Email:</b> <a href="mailto:contact@obscuron.faizath.com">contact@obscuron.faizath.com</a> (formerly <i>contact@obscuron.chat</i>)<br>
        🛰️ <b>CDN:</b> <a>obscuron-cdn.faizath.com</a> (formerly <i>cdn.obscuron.chat</i>)<br>
        📈 <b>Status Pages:</b> <a href="https://status.faizath.com/status/obscuron">https://status.faizath.com/status/obscuron</a> (formerly <i>status.obscuron.chat</i>)
        </p>
      </td>
    </tr>
  </table>
</div>

# Obscuron Chat

## About
Obscuron Chat is a secure messaging application built with three components:
- **obscuron-web**: React + TypeScript frontend interface
- **nodejs-api**: Node.js API backend with MongoDB integration
- **flask-api**: Flask API backend for additional services

## Installation
1. Clone repositories:
```bash
git clone https://github.com/obscuron/obscuron-web.git
git clone https://github.com/obscuron/nodejs-api.git
git clone https://github.com/obscuron/flask-api.git
```

2. Configure environment variables:
```bash
# nodejs-api/.env
MONGODB_URI=mongodb://...
JWT_SECRET=your-secret-key
PORT=3000
DEBUG=true
```

3. Install dependencies:
```bash
# For React client
cd obscuron-web && npm install

# For Node.js backend
cd nodejs-api && npm install

# For Flask backend
cd flask-api && pip install -r requirements.txt
```

4. Build Docker images:
```bash
# For client
cd obscuron-web && docker build -t obscuron-web .

# For Node.js API
cd nodejs-api && docker-compose up --build
```

## Usage
1. Start backend services:
```bash
# Node.js API (in separate terminals)
cd nodejs-api && docker-compose up

# Flask API
cd flask-api && python3 app.py
```

2. Launch frontend:
```bash
cd obscuron-web && npm run dev
```

## Tech Stack
- **Frontend**: React 18 + TypeScript + Tailwind CSS
- **Node.js Backend**: Express.js + MongoDB + Cloudflare R2 + JWT
- **Flask Backend**: Python 3.11 + Flask
- **Containerization**: Docker + Docker Compose
- **Development Tools**: Vite (client), ESLint (client), WebSocket (real-time chat)

## API Endpoints
- **Node.js API**:
  - WebSocket: `ws://localhost:3000/room/:id`
  - HTTP API:
    - `POST /auth` - Authentication/Registration
    - `POST /profile` - Profile Updates
    - `GET /users` - User Listing

- **Flask API**:
  - Available routes defined in `flask-api/app.py`