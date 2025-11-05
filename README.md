# Sputnik Subject - Master's Thesis Project

## Project Description

This project involves the creation of a conversational agent using the Rasa framework and local integration with Llama 3.1 through Ollama. The goal is to create an NPC powered by generative AI that can maintain a conversation following a context and game objectives, allowing users to experiment with concepts of humanity, emotions, and ethics, among others, with a cybernetic being.

## Context and Objectives

To provide users with a context for maintaining a conversation with Sputnik, the following scenario was chosen:

"Sputnik was the first artificial satellite launched into space, which constituted a milestone in the history of technology. However, the Sputnik before you is not the satellite, but the first artificial android subject with human appearance, voice, and characteristics. It is created to possess all existing knowledge, possess superior intelligence, perhaps be better than any human being. Its appearance recalls a clean and neat being due to its white hair, pale skin, and very light blue eyes. However, would such a being be capable of coexisting in society? Of understanding the complex emotional processes of human beings and their characteristic way of behaving in the world? Will it be able to distinguish right from wrong, act with justice? Your task as a researcher is to sit and talk with it in a room for a while, and try to discover who Sputnik is and whether its mere existence represents a threat or not. When you enter, you see it with a book in its hands. What is the first thing you will say to it?"

To enhance the experience, users must gather information about the following four questions within a limit of 15 interactions:

1. **Discover Sputnik's identity capacity**: It is interesting to know if Sputnik understands its origin, who it is, who created it, or for what purpose. Additionally, it is important to discover if it understands that it is an artificial intelligence.
2. **Understand its relationship and knowledge about human emotions**: This objective is a pillar in the conversation, that is, discovering what it understands and doesn't understand about human emotions, what it thinks about them, how it would be able to relate to beings who feel them constantly, etc.
3. **Explore its philosophical perspective**: Another topic to address is its perspective on philosophical questions such as life or death, ethics or morality, consciousness, or the meaning of existence itself. Will it be different from ours?
4. **Learn about its sources of knowledge**: When we enter the room, we see Sputnik reading a book, and it is likely to give us information about it and what it has evoked in it. Why not take the opportunity to discover what sources are nourishing its information about human behavior and nature?

## System Requirements

- **Operating System**: Windows 10/11, macOS 10.15+, or Ubuntu 18.04+
- **RAM**: Minimum 8GB (16GB recommended)
- **Disk Space**: At least 10GB free
- **Internet Connection**: Required for initial downloads

## Installation and Configuration

### 1. Download and Install Visual Studio Code (only if not already installed)

Follow these instructions:

1. Go to the official website: https://code.visualstudio.com/
2. Download directly by clicking "Download"

### 2. Install Ollama and Llama 3.1

#### 2.1 Install Ollama

**For Windows and MacOS**:

Follow these instructions:

1. Visit the official Ollama page: https://ollama.ai/
2. Click "Download", select your operating system, and follow the instructions

**For Linux**:

Install from the terminal using the following command:

```bash
curl -fsSL https://ollama.ai/install.sh | sh
```

#### 2.2 Install the Llama 3.1 Model

Once Ollama is installed, open a terminal:
- **For Windows**: Press Windows Key + X and select Windows Terminal (Administrator), or type "cmd" in the Start menu search and select Command Prompt
- **For MacOS**: Open from the Terminal application, which can be found in Applications
- **For Linux**: Press Ctrl + Alt + T. You can also find the terminal application in the system applications menu, searching for terms like "Terminal" or "Console"

When you have opened the terminal, execute the following command:

```bash
ollama pull llama3.1
```

**Note**: This download may take several minutes depending on your internet connection, as the model is several GB in size.

#### 2.3 Verify the Installation

It is recommended to verify that the model is working correctly after downloading. To do this, run the following in the terminal:

```bash
ollama run llama3.1
```

If an interactive prompt appears, everything is working correctly. To exit, simply run `/bye`

### 3. Clone and Configure the Project

#### 3.1 Clone the Repository

To clone the Rasa directory, follow these steps:

1. Open Visual Studio Code
2. Open a terminal from View > Terminal
3. Navigate to the desired directory on your computer:

**For Windows**: 

```bash
cd C:\Users\[your-username]\Documents
```

**For MacOS/Linux**: 

```bash
cd ~/Documents
```

4. Clone the repository using the following commands:
   
```bash
git clone https://github.com/liseai?tab=repositories
cd Master-Final-Project
```

#### 3.2 Create Python Virtual Environment

It is recommended to create a virtual environment for the project, so that all project dependencies can be downloaded within the same environment, and not within the general directory of the computer. To do this, follow these steps:

1. Verify that you have Python version 3.8 or higher installed. To do this, in the terminal (can be within VSC), run:
   
```bash
python --version
```

If you don't have Python installed, you can download it from https://www.python.org/

2. Create the virtual environment (in our case, from VSC):
- Open the Command Palette (Ctrl+Shift+P on Windows, or Cmd+Shift+P on MacOS)
- Type in the palette `Python: Create Environment` and choose the option that appears to create a new virtual environment (usually Venv)
- Select "Venv: Creates a '.venv' virtual environment in the current workspace"
- Select the Python version to use in the virtual environment

With this, VS Code will create the virtual environment and automatically configure it for the project.
To confirm that the environment is active, you should see `(venv)` at the beginning of the command line.

### 4. Install Dependencies

With the virtual environment activated, install the requirements by running the following (separately):

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

**Note**: This process may take several minutes.

### 5. Train and Run the Rasa Model

To perform the following, it is important that you verify that Ollama is active (it's enough to open the application we downloaded previously or run `ollama serve` in a terminal).
Once it is, follow these steps:

#### 5.1 Train the Model

Again, with the virtual environment active in VSC, run:

```bash
rasa train
```

#### 5.2 Start the Actions Server

In a new terminal, keeping the previous one open, and verifying that the environment is still active in this new one, run:

```bash
rasa run actions
```

#### 5.3 Run the Assistant

In the original terminal or a new one, run:

```bash
rasa shell
```

After a few minutes, if everything has worked correctly, you should be able to interact with the assistant.


