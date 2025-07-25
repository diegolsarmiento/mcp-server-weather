# 🌦️ MCP Weather Tool Server

This is a local [Model Context Protocol (MCP)](https://modelcontextprotocol.io) server that provides weather data using the [Open-Meteo API](https://open-meteo.com/). It's designed to work with Claude Desktop and other MCP-compatible clients.

## 🛠 Features

- `get_current_weather`: Returns current weather conditions (temperature, wind gusts, cloud cover, etc.)
- `get_forecast`: Returns daily forecast for the next several days
- Built with [`fastmcp`](https://pypi.org/project/fastmcp/) for rapid MCP tool development

---

## 🚀 Setup

### 1. Clone the repo

```bash
git clone https://github.com/diegolsarmiento/mcp-server-weather.git
cd mcp-server-weather
````

### 2. Create a virtual environment (optional but recommended)

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

If you don’t have a `requirements.txt`, install manually:

```bash
pip install fastmcp httpx
```

---

## 🧪 Run the server

```bash
python weather_server.py
```

This will launch the server using standard input/output (`stdio`) for Claude Desktop compatibility.

---

## 🔌 MCP Config Example

Add this to your Claude Desktop config (`Edit Config` → Developer tab):

```json
{
  "mcpServers": {
    "weather": {
      "command": "python3",
      "args": [
        "/Users/YOUR_USERNAME/path/to/mcp-server-weather/weather_server.py"
      ]
    }
  }
}
```

✅ After saving, restart Claude and click the 🛠 icon to use your tools.

---

## 🌐 API Used

[Open-Meteo API](https://open-meteo.com/): Free, no-auth weather data provider.

---

## 📁 File Structure

```
mcp-server-weather/
├── weather_server.py   # Main MCP tool server
├── README.md           # You're here
```

---

## 📌 Notes

* Make sure your Claude Desktop app is running in Developer Mode.
* Tools return data as strings (using `json.dumps`) to match the current output schema.
* You can inspect tool calls using [MCP Inspector](https://modelcontextprotocol.io/docs/tools/inspector#inspecting-locally-developed-servers).

---

## 🧑‍🚀 Author

Made by [@diegolsarmiento](https://github.com/diegolsarmiento)
