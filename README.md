# VA Assistant

This `README.md` provides instructions on how to set up and run the `va-assistant.py` program.

---

## Prerequisites

Before running the program, ensure you have **Python 3.9.x** installed on your system. This project is intended to be run directly on **Windows** to avoid audio configuration complexities associated with WSL.

---

## Required Packages

The following Python packages are necessary to run the VA Assistant:

* **`python-dotenv`**: For loading environment variables from a `.env` file.
* **`elevenlabs`**: The client library for interacting with the ElevenLabs API for conversational AI.
* **`pyaudio`**: Required for audio input/output, which the `elevenlabs` conversational AI components use.

---

## Installation

Follow these steps to set up your environment and install the required packages:

1.  **Create a Virtual Environment** (Recommended):
    It's best practice to use a virtual environment to manage project dependencies. Open your command prompt or PowerShell on Windows and navigate to your project directory.

    ```powershell
    python -m venv venv
    ```

2.  **Activate the Virtual Environment**:
    Once created, activate the virtual environment:

    ```powershell
    .\venv\Scripts\activate
    ```
    You should see `(venv)` at the beginning of your command prompt, indicating the virtual environment is active.

3.  **Install Required Python Packages**:
    With the virtual environment activated, install the necessary packages using `pip`:

    ```powershell
    pip install python-dotenv elevenlabs pyaudio
    ```

    *If you encounter issues installing `pyaudio`*, it might be due to missing system-level audio development headers. However, running directly on Windows generally simplifies this. If problems persist, ensure your Python installation includes the necessary development files or refer to PyAudio's official documentation for specific Windows installation prerequisites.

---

## Environment Variables

The program requires `AGENT_ID` and `API_KEY` to be set as environment variables. Create a file named `.env` in the root of your project directory (the same location as `va_assistant.py`) and add your credentials:

```ini
AGENT_ID="your_elevenlabs_agent_id_here"
API_KEY="your_elevenlabs_api_key_here"
```
**Important:** Do **not** commit this `.env` file to version control (e.g., Git). Make sure to add `.env` to your `.gitignore` file. If you previously committed it, use `git rm --cached .env` and then commit the change.

---

## How to Run the Program

After installing the packages and setting up your `.env` file, you can run the VA Assistant:

1.  **Ensure your Virtual Environment is Active**.
2.  **Run the script**:

    ```powershell
    python va_assistant.py
    ```

    The program should start, and you will see output from the `print_agent_response`, `print_interrupted_response`, and `print_user_transcript` callbacks if the conversational AI interaction proceeds as expected.
