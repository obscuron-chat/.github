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
Obscuron Chat is a secure messaging application built with three core components:
- **obscuron-client**: React + TypeScript frontend interface
- **nodejs-core**: Node.js API backend with MongoDB integration
- **flask-core**: Flask API backend for additional services

## Installation
1. Clone repositories:
```bash
git clone https://github.com/obscuron/obscuron-client.git
git clone https://github.com/obscuron/nodejs-core.git
git clone https://github.com/obscuron/flask-core.git
```

2. Configure environment variables:
```bash
# nodejs-core/.env
MONGODB_URI=mongodb://...
JWT_SECRET=your-secret-key
PORT=3000
DEBUG=true
```

3. Install dependencies:
```bash
# For React client
cd obscuron-client && npm install

# For Node.js backend
cd nodejs-core && npm install

# For Flask backend
cd flask-core && pip install -r requirements.txt
```

4. Build Docker images:
```bash
# For client
cd obscuron-client && docker build -t obscuron-client .

# For Node.js core
cd nodejs-core && docker-compose up --build
```

## Usage
1. Start backend services:
```bash
# Node.js core (in separate terminals)
cd nodejs-core && docker-compose up

# Flask core
cd flask-core && python3 app.py
```

2. Launch frontend:
```bash
cd obscuron-client && npm run dev
```

## Tech Stack
- **Frontend**: React 18 + TypeScript + Tailwind CSS
- **Node.js Backend**: Express.js + MongoDB + Cloudflare R2 + JWT
- **Flask Backend**: Python 3.11 + Flask
- **Containerization**: Docker + Docker Compose
- **Development Tools**: Vite (client), ESLint (client), WebSocket (real-time chat)

## API Endpoints
- **Node.js Core**:
  - WebSocket: `ws://localhost:3000/room/:id`
  - HTTP API:
    - `POST /auth` - Authentication/Registration
    - `POST /profile` - Profile Updates
    - `GET /users` - User Listing

- **Flask Core**:
  - Available routes defined in `flask-core/app.py`