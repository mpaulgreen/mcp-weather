### Sample Project

- Execute the following command  to initialize the project
```
# Create a new directory for our project
uv init weather
cd weather

# Create virtual environment and activate it
uv venv
source .venv/bin/activate

# Install dependencies
uv add "mcp[cli]" httpx

# Create our server file
touch weather.py
```
- Create the weather tools
https://github.com/mpaulgreen/mcp-weather/blob/main/weather.py

- Start the mcp server
```
uv run weather.py
```

- Add this to claude_desktop_config.json
```
{
    "mcpServers": {
        "weather": {
            "command": "/opt/homebrew/bin/uv",
            "args": [
                "--directory",
                "/Users/mrigankapaul/Documents/knowledgebase/crewai/weather",
                "run",
                "weather.py"
            ]
        }
    }
}
```
- Restart the desktop
- Try with 
```
What’s the weather in Sacramento?
What are the active weather alerts in Texas?
```