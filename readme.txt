# Personal Assistant

A simple Python personal assistant chatbot that uses NLP intent classification to understand user messages and respond with predefined answers. The assistant can handle basic conversations, identify user intents, and provide voice output using text-to-speech.

## Features

- Intent-based chatbot responses
- Natural language preprocessing with NLTK
- Bag-of-words text representation
- Neural network intent classification
- Text-to-speech support
- Customizable intents and responses
- Simple command-line interaction

## Technologies Used

- Python
- TensorFlow
- TFLearn
- NLTK
- NumPy
- gTTS
- pyttsx3

## Project Structure

```text
Personal-Assistant/
├── main.py
├── intents.json
├── data.pickle
├── model.tflearn.data-00000-of-00001
├── model.tflearn.index
├── model.tflearn.meta
└── readme.txt
```

## How It Works

The assistant uses a JSON file containing intents, example patterns, and possible responses. During training, the text patterns are tokenized, stemmed, and converted into a bag-of-words representation. A neural network is then trained to classify user input into one of the predefined intent categories.

When the user enters a message, the assistant predicts the most likely intent and returns a random response from that category.

## Installation

Clone the repository:

```bash
git clone https://github.com/chrispsk/Personal-Assistant.git
cd Personal-Assistant
```

Install the required dependencies:

```bash
pip install nltk numpy tensorflow tflearn gTTS pyttsx3 playsound
```

Depending on your Python version, you may need older package versions because this project was built using older TensorFlow and TFLearn releases.

Recommended legacy setup:

```bash
pip install tensorflow==1.4 tflearn==0.3.2
```

## Usage

Run the assistant with:

```bash
python main.py
```

Then type a message in the terminal and the assistant will respond based on the trained intents.

Example:

```text
You: hello
Assistant: Hello!

You: what are your hours?
Assistant: We are open 7am-4pm Monday-Friday!
```

## Customizing the Assistant

You can add new intents by editing `intents.json`.

Example:

```json
{
  "tag": "thanks",
  "patterns": ["thanks", "thank you", "that's helpful"],
  "responses": ["You're welcome!", "Happy to help!", "Anytime!"]
}
```

After changing the intents file, delete the existing model/data files and run the project again so the assistant can retrain.

Files to regenerate:

```text
data.pickle
model.tflearn.data-00000-of-00001
model.tflearn.index
model.tflearn.meta
```

## Possible Improvements

- Add a `requirements.txt` file
- Add more intents and training examples
- Separate training and chat logic into different files
- Add error handling
- Add tests
- Update the project to use modern TensorFlow/Keras
- Improve voice interaction
- Add a graphical interface or web interface
