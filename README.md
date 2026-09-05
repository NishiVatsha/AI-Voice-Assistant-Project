# AI Voice Assistant Project



A Python-based voice assistant that accepts spoken commands, responds using speech, provides the current date and time, and allows users to set voice-based reminders.

## Features

* **Voice Command Recognition** — Captures user commands through a microphone using SpeechRecognition.
* **Text-to-Speech** — Provides spoken responses using pyttsx3.
* **Date and Time** — Provides the current date and time when requested.
* **Voice-Based Reminders** — Allows users to create reminders by specifying a task, hour, and minute.
* **Background Reminder Checking** — Uses Python threading to continuously monitor scheduled reminders.
* **English Speech Recognition** — Uses Google's speech recognition service with `en-in` language support.

## Technologies Used

* Python
* SpeechRecognition
* pyttsx3
* PyAudio
* datetime
* threading
* time

## Project Structure

```text
AI-Voice-Assistant-Project/
│
├── voice_assistant.py
├── README.md
└── requirements.txt
```

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Nishu1312/AI-Voice-Assistant-Project.git
cd AI-Voice-Assistant-Project
```

### 2. Install Dependencies

```bash
pip install SpeechRecognition pyttsx3 PyAudio
```

Or, if you have a `requirements.txt` file:

```bash
pip install -r requirements.txt
```

## Running the Project

Run the Python file:

```bash
python voice_assistant.py
```

The assistant will greet the user and begin listening for voice commands.

## Available Commands

### Date and Time

Ask:

```text
What is the time?
```

or:

```text
What is today's date?
```

The assistant will provide the current date and time.

### Set a Reminder

Say:

```text
Set a reminder
```

The assistant will ask:

1. What should I remind you about?
2. At what hour?
3. What minute?

Example:

```text
User: Set a reminder
Assistant: What should I remind you about?
User: Complete my assignment
Assistant: At what hour should I remind you?
User: 18
Assistant: And what minute?
User: 30
```

The assistant will notify you when the scheduled time is reached.

### Exit

The assistant can be stopped by saying:

```text
Exit
```

```text
Stop
```

or:

```text
Bye
```

## How It Works

1. The program initializes the voice assistant.
2. The microphone captures the user's voice.
3. SpeechRecognition converts the voice input into text.
4. The program identifies the requested command.
5. The appropriate function is executed.
6. pyttsx3 converts the response into speech.
7. A background thread continuously checks scheduled reminders.

## Multithreading

The reminder system runs in a separate daemon thread:

```python
threading.Thread(target=check_reminders, daemon=True).start()
```

This allows the assistant to continue listening for commands while the reminder system checks the scheduled times in the background.

## Limitations

* Reminders are stored only in memory and are lost when the program is closed.
* A working microphone is required.
* Speech recognition requires an internet connection.
* The current implementation supports English (India) speech recognition.
* Reminders are currently designed for the current day.

## Future Improvements

* Add persistent reminder storage using JSON or a database.
* Support natural-language reminder times.
* Add weather and web search functionality.
* Add application and system-control commands.
* Support multiple languages.
* Add a graphical user interface.
* Improve speech recognition and error handling.

## Author

**Nishi Vatsha**

## License

This project is created for educational and learning purposes.
