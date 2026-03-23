# Set Card Game – Java Concurrency & Synchronization

## 📌 Overview

This project is a Java implementation of the card game **Set**, focusing on **multithreading, synchronization, and concurrent system design**.

The system simulates a real-time multiplayer game where multiple players interact with a shared table while a dealer coordinates the game flow.

---

## 🧠 Key Concepts Demonstrated

* Java Threads
* Synchronization & Shared Resources
* Producer–Consumer patterns
* Thread coordination and communication
* Avoiding race conditions and deadlocks
* Concurrent game logic simulation

---

## 🏗️ System Architecture

### 🔹 Dealer (Main Thread)

* Manages the game lifecycle
* Deals and reshuffles cards
* Validates player actions (sets)
* Maintains game timing and flow

### 🔹 Players (Multiple Threads)

* Each player runs in its own thread
* Maintains a queue of actions (token placements)
* Competes concurrently to identify valid sets

### 🔹 Table (Shared Resource)

* Represents the game board
* Synchronizes access between dealer and players
* Tracks cards and player tokens

---

## ⚙️ How It Works

1. The dealer places cards on the table.
2. Players (threads) place/remove tokens concurrently.
3. Once a player selects 3 cards, they request validation.
4. The dealer checks if the set is valid:

   * ✔️ Valid → player earns a point, cards replaced
   * ❌ Invalid → player receives a penalty (freeze)
5. The game continues until no valid sets remain.

---

## 🚀 How to Run

### Requirements

* Java 17+
* Maven

### Run the project

```bash
mvn clean compile
mvn exec:java
```

---

## 📂 Project Structure

```text
.
├── pom.xml
├── src/
│   ├── main/java/bguspl/set/        # Framework & infrastructure (provided)
│   ├── main/java/bguspl/set/ex/     # Core game logic (implemented by me)
│   ├── main/resources/              # Config + card images
│   └── test/java/                  # Unit tests
```

---

## ✍️ My Contribution

The core logic of the system was implemented in:

```text
src/main/java/bguspl/set/ex/
```

Including:

* Dealer logic (game flow & synchronization)
* Player behavior and action handling
* Table synchronization and shared state management

---

## 🧪 Testing

* Unit tests provided and extended (`PlayerTest`, `TableTest`)
* Manual testing via GUI gameplay

---

## 🎯 Challenges & Solutions

* Ensuring fair access between competing player threads (FIFO handling)
* Preventing race conditions on shared game state
* Coordinating threads without excessive locking
* Managing player freeze/penalty timing correctly
* Maintaining responsiveness while ensuring correctness

---

## 🛠️ Technologies

* Java
* Maven
* Multithreading (Threads)
* Synchronization primitives

---

## 👤 Author

**Idan Oshri**
Computer Science Graduate

---
