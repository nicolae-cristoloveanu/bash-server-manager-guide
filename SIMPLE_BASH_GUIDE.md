# Simple Bash Guide to Python's HTTP Server

Quick reference for using Python's built-in HTTP server with essential bash commands.



Key Features of the Guide:

🚀 Primary Functionality
•  Starting server: python3 -m http.server
•  Clear explanation of what the command does (port 8000, current directory, localhost access)

🔍 Finding Server Instances
•  Command: ps aux | grep http.server
•  Shows how to identify running processes with PID
•  Includes example output for clarity

🛑 Stopping the Server
•  Three methods: Ctrl+C, kill by PID, kill all servers
•  Clear explanations of what each command does
•  Safety considerations for pkill -f http.server

🔄 Restarting
•  Step-by-step restart process
•  One-line restart command option
•  Logical workflow sequence

📝 Quick Reference
•  4-step workflow: Start → Check → Stop → Restart
•  Essential tips for development use
•  Security note (localhost only)




## Starting the Server

```bash
python3 -m http.server
```

**What this does:**
- Starts HTTP server on port 8000
- Serves files from current directory
- Access at: http://localhost:8000

## Finding Running Server Instances

```bash
ps aux | grep http.server
```

**What this does:**
- Shows all running Python HTTP server processes
- Displays process ID (PID) and details
- Helps identify which servers are active

**Example output:**
```
user    12345  0.1  0.2  python3 -m http.server
user    12346  0.1  0.2  python3 -m http.server 8080
```

## Stopping the Server

### Method 1: Direct Stop
Press `Ctrl+C` in the terminal where server is running

### Method 2: Kill by PID
```bash
kill 12345
```

**What this does:**
- Stops the server process with ID 12345
- Replace 12345 with actual PID from `ps aux` command

### Method 3: Kill All HTTP Servers
```bash
pkill -f http.server
```

**What this does:**
- Stops all Python HTTP server processes at once
- Use with caution if running multiple servers

## Restarting the Server

```bash
# Stop the server first
kill 12345

# Start it again
python3 -m http.server
```

**Or in one line:**
```bash
pkill -f http.server && python3 -m http.server
```

## Quick Workflow

1. **Start**: `python3 -m http.server`
2. **Check**: `ps aux | grep http.server`
3. **Stop**: `kill <PID>` or `Ctrl+C`
4. **Restart**: Kill then start again

## Tips
- Server runs until manually stopped
- Only accessible from your local machine (secure)
- Serves static files (HTML, CSS, JS, images, etc.)
- Perfect for quick testing and development
