# chat-application-using-java-
chat application using java 
Here’s a README file template for your **Chat Application using Java** project, based on the code you shared:

---

# Chat Application Using Java

This project is a **real-time chat application** developed using **Java** with a graphical user interface (GUI) built using **Swing**. The application allows users to exchange messages, use text formatting (bold, italic, underline), insert emojis, and store/load chat history from a MySQL database.

## Features
- **Real-time chat**: Users can send and receive messages in real time.
- **Text Formatting**: Messages can be formatted with bold, italic, and underline styles.
- **Emoji Support**: Users can insert emojis into their messages.
- **Message History**: Previous chat messages are loaded from a database when the user logs in.
- **Message Storage**: Messages are stored in a MySQL database, with a timestamp for each message.

## Technologies Used
- **Java (Swing)**: For building the graphical user interface (GUI).
- **MySQL**: For storing and retrieving chat messages.
- **JDBC (Java Database Connectivity)**: For connecting to the MySQL database.
- **JTextPane**: For managing the chat area and input fields with text styling.

## Project Structure
The key components of the application are as follows:

- **ChatWindow.java**: The main class that creates the chat window for sending and receiving messages.
- **Database Configuration**: The database is set up using JDBC for storing chat messages with the following parameters:
  - **DB_URL**: `jdbc:mysql://localhost:3306/ChatDB`
  - **DB_USER**: `root`
  - **DB_PASSWORD**: `Morya@123`

### User Interface Components
- **chatArea**: Displays the chat messages exchanged between users.
- **inputField**: The text input area where users type their messages.
- **emojiComboBox**: Dropdown list of emojis users can insert into their messages.
- **boldButton, italicButton, underlineButton**: Buttons for toggling bold, italic, and underline text formatting.
- **sendButton**: Button to send the typed message.

## Getting Started

### Prerequisites
To run this project, ensure you have the following installed:
- **Java Development Kit (JDK) 8 or above**
- **MySQL Server**
- **An IDE** like IntelliJ IDEA, Eclipse, or NetBeans

### Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/omraje2424/chat-application-using-java.git
   ```

2. **Database Setup**:
   - Create a MySQL database named `ChatDB`.
   - Create a table `chat_messages` with the following structure:
     ```sql
     USE ChatDB;

CREATE TABLE users (
    user_id INT AUTO_INCREMENT PRIMARY KEY,   -- Unique user ID (auto-incrementing)
    username VARCHAR(50) NOT NULL UNIQUE,     -- Username (must be unique)
    password VARCHAR(100) NOT NULL,           -- Password (hashed passwords recommended)
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP -- Timestamp when the user was created
);
-- Table for storing chat sessions
CREATE TABLE IF NOT EXISTS chat_sessions (
    session_id INT AUTO_INCREMENT PRIMARY KEY,
    user1 VARCHAR(50) NOT NULL,
    user2 VARCHAR(50) NOT NULL,
    UNIQUE(user1, user2)
);

-- Table for storing messages within a session
CREATE TABLE IF NOT EXISTS chat_messages (
    message_id INT AUTO_INCREMENT PRIMARY KEY,
    session_id INT NOT NULL,
    sender VARCHAR(50) NOT NULL,
    message TEXT NOT NULL,
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (session_id) REFERENCES chat_sessions(session_id) ON DELETE CASCADE
);
     ```

3. **Configure Database Credentials**:
   - In the `ChatWindow.java` file, modify the `DB_URL`, `DB_USER`, and `DB_PASSWORD` to match your MySQL configuration.

4. **Run the Application**:
   - Open the project in your preferred IDE.
   - Compile and run the `ChatWindow.java` file.

### Running the Chat Application
- When the application starts, it creates a chat window for a user.
- Users can type their messages in the **inputField**, format them, and send them using the **sendButton**.
- The **chatArea** will display sent and received messages in real time.
- Emoji support is provided via the **emojiComboBox**, allowing users to add emojis to their messages.

## Future Enhancements
- **Multiple User Support**: Add functionality for multiple users to join the same chat session.
- **Private Messaging**: Enable private chat rooms between selected users.
- **Message Encryption**: Implement encryption for securing chat messages.


## Screenshots
![Screenshot 2024-10-21 204603](https://github.com/user-attachments/assets/d723f761-14c0-4bea-9ed5-ee04a28991f9)

![Screenshot 2024-10-21 204653](https://github.com/user-attachments/assets/816c5668-8117-4c0a-adbf-2f3683d8f686)

![Screenshot 2024-10-21 204739](https://github.com/user-attachments/assets/d247107c-6813-4fc7-8be4-112ac1d4231e)

![Screenshot 2024-10-21 204823](https://github.com/user-attachments/assets/a8daf207-5064-48ce-a2ee-e734627b1857)

![Screenshot 2024-10-21 204900](https://github.com/user-attachments/assets/8fc539b5-bde8-42a9-b787-f64018d0e4e7)

![Screenshot 2024-10-21 204943](https://github.com/user-attachments/assets/5f75212a-a4c8-4e88-847c-0b8528ffca88)

![Screenshot 2024-10-21 205028](https://github.com/user-attachments/assets/340ee0b5-7f25-4442-81d5-8c5d82e8f7a4)






