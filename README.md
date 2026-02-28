# How to Start the BitFeed Automation Program

You can trigger the pipeline to fetch AI news directly using a single curl command if the API backend server is running. You can control exactly how many articles it generates by simply changing the `count` parameter in the URL.

## Step 1: Start the Backend Server (One-Time Setup)
Open a terminal in the `bitfeed-auto` directory and run these commands to turn on the scraping and generation engine:

```bash
# Activate the virtual environment
source .venv/bin/activate

# Start the server (runs on http://0.0.0.0:8000)
python automation.py
```

## Step 2: Trigger Generation via Terminal Command
Now that the server is listening, open a **new** terminal tab/window.
Whenever you want to generate articles, run this single `curl` command.

**To generate exactly 5 articles**:
```bash
curl -N "http://0.0.0.0:8000/run-all?count=5"
```

**To generate exactly 12 articles**:
```bash
curl -N "http://0.0.0.0:8000/run-all?count=12"
```

*(The `-N` flag tells curl to stream live progress directly to your terminal. It will save the scraped articles in the `output/` folder and generated JSON to the `article/` folder.)*

## Step 3: Stop the Server
When you're entirely done, return to the first terminal running the server and press `Ctrl + C` to stop it. Then, to exit the virtual environment, just type:
```bash
deactivate
```
