🚀 NeuroNavigator – MCP Browser Agent

An intelligent MCP-powered browser automation agent built with Playwright and designed to work seamlessly with Claude Desktop.

NeuroNavigator transforms natural language instructions into real-time browser automation, API interactions, and multi-step workflows — enabling true AI-driven task execution.

✨ Why NeuroNavigator?

Unlike simple automation scripts, NeuroNavigator acts as a stateful AI agent:

Maintains persistent browser sessions

Chains multi-step operations

Recovers intelligently from errors

Captures console logs and screenshots

Executes API requests alongside browser actions

It bridges natural language → browser control → API interaction → structured output.

🌐 Core Features
🔹 Advanced Browser Automation

Navigate to any URL with customizable load strategies

Capture full-page or element-level screenshots

Click, fill, hover, and select elements precisely

Execute arbitrary JavaScript in the browser context

Capture and expose browser console logs

🔹 Powerful API Client

Perform HTTP requests (GET, POST, PUT, PATCH, DELETE)

Configure headers and request bodies

Automatic JSON response formatting

Detailed error handling and feedback

🔹 MCP Resource Management

Access browser logs via browser://logs

Retrieve screenshots via screenshot://[name]

Persistent headful browser sessions

Stateful execution across multiple commands

🔹 AI Agent Capabilities

Chain multiple browser operations

Execute complex multi-step workflows

Intelligent error recovery

Automate technical tasks through natural language

🎥 Demo

NeuroNavigator MCP Server Demo
(Insert demo video or GIF here)

🧰 Requirements

Node.js 16+

Claude Desktop

Playwright dependencies

🌍 Browser Support

Supported browsers:

Chrome (default)

Firefox

Microsoft Edge

WebKit (Safari engine)

Initialize Playwright:

npm init playwright@latest

Install specific browsers manually if needed:

npx playwright install chrome
npx playwright install firefox
npx playwright install webkit
npx playwright install msedge

Note:

Safari is supported via WebKit (not native Safari).

Edge is launched via Chromium with the msedge channel.

📦 Installation
Manual Installation
git clone (https://github.com/bhavya0ps/NeuroNavigator/tree/main)
cd mcp-browser-agent
npm install
npm run build
▶ Running the MCP Server
Option 1: Manual Run
node dist/index.js

Keep the terminal open while using Claude Desktop.

Option 2: Auto-Start with Claude Desktop (Recommended)

Edit:

macOS

~/Library/Application Support/Claude/claude_desktop_config.json

Windows

%APPDATA%\Claude\claude_desktop_config.json

Linux

~/.config/Claude/claude_desktop_config.json

Add:

{
  "mcpServers": {
    "browserAgent": {
      "command": "node",
      "args": [
        "ABSOLUTE_PATH_TO_DIRECTORY/mcp-browser-agent/dist/index.js",
        "--browser",
        "chrome"
      ]
    }
  }
}

Replace ABSOLUTE_PATH_TO_DIRECTORY with your full system path.

🌎 Browser Selection Options
1️⃣ Config File

Create:

~/.mcp_browser_agent_config.json
{
  "browserType": "chrome"
}

Supported values:

chrome

firefox

webkit

edge

2️⃣ Command Line
node dist/index.js --browser firefox
3️⃣ Environment Variable
MCP_BROWSER_TYPE=firefox node dist/index.js
🧠 Technical Architecture

NeuroNavigator is built on Model Context Protocol and consists of four main components:

1️⃣ Server (index.ts)

Initializes MCP server

Configures tools and resources

Establishes stdio communication with Claude

2️⃣ Tools Registry (tools.ts)

Defines browser & API schemas

Validates parameters

Registers tools for discovery

3️⃣ Request Handlers (handlers.ts)

Routes MCP tool calls

Exposes logs and screenshots as resources

4️⃣ Executor (executor.ts)

Manages browser lifecycle

Implements Playwright automation

Handles API requests

Maintains session state

🛠 Available Tools
Browser Tools
Tool	Description
browser_navigate	Navigate to URL
browser_screenshot	Capture screenshot
browser_click	Click element
browser_fill	Fill input
browser_select	Select dropdown
browser_hover	Hover element
browser_evaluate	Execute JavaScript
API Tools
Tool	Description
api_get	GET request
api_post	POST request
api_put	PUT request
api_patch	PATCH request
api_delete	DELETE request
📂 Resource Access

browser://logs → Browser console logs

screenshot://[name] → Access stored screenshots

💡 Example Workflows
Basic Navigation

Navigate to Google

Take screenshot

Search for weather forecast

Form Automation

Login to demo site

Fill username & password

Submit form

JavaScript Execution

Count links on page

Extract page title

API Automation

Perform GET request

Send structured POST data

🛠 Development

Build:

npm run build

Watch mode:

npm run watch

Testing:

npm test
npm run test:watch
npm run test:coverage

Tests verify:

Browser automation

Error handling

Process cleanup

Configuration integrity

🔒 Security Considerations

This project provides autonomous browser control.

Users are responsible for:

Complying with website terms of service

Following ethical automation practices

Ensuring lawful usage

🤝 Contributing

We welcome contributions:

New browser capabilities

Improved error recovery

Enhanced resource management

Performance optimization

Example workflows

📜 License

Licensed under Mozilla Public License 2.0.

🌟 Vision

NeuroNavigator is more than browser automation.

It is a foundation for:

AI-powered RPA

Research automation

DevOps agents

Business workflow automation

Autonomous web agents
