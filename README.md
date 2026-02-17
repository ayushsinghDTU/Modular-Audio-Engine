# 🎵 RhythmBox

A modular, console-based **C++11 music player** featuring an interactive menu-driven interface and professional design patterns implementation.

## 📖 Project Description

RhythmBox is a practical demonstration of Object-Oriented Programming (OOP), SOLID principles, and real-world software design patterns in C++. It provides a clean, extensible architecture for managing music libraries, creating playlists, controlling playback, and dynamically connecting audio devices through an intuitive command-line interface.

---

## 🎯 Key Features

### 🎶 Music Library & Playlists

- Create and manage songs in a centralized library
- Create multiple custom playlists
- Add and remove songs from playlists
- Delete playlists dynamically

### ▶️ Playback Control

- Play full playlists or individual tracks
- Switch between **Sequential Mode** (in-order playback) and **Random Mode** (shuffled playback)
- Navigate tracks using **Next** and **Previous** controls
- Playback behavior changed at runtime without modifying existing code

### 🔌 Device Simulation

- Simulate dynamic connection of audio output devices:
  - 🎧 Headphones
  - 🔊 Bluetooth Speaker
  - 🔌 Wired Speaker
- Devices can be switched during execution, demonstrating runtime abstraction and loose coupling

---

## 🏛️ Design Patterns Implemented

### 🔹 Facade Pattern

**MusicPlayerFacade** provides a simplified high-level interface to complex subsystems, hiding internal complexity and offering a unified access point for all operations.

### 🔹 Singleton Pattern

Managers, Facade, and Application class ensure single, globally accessible instances, preventing multiple instantiations and maintaining consistent state throughout the application.

### 🔹 Strategy Pattern

**PlayStrategy Interface** with concrete implementations:
- **SequentialPlayStrategy** - Plays songs in order
- **RandomPlayStrategy** - Plays songs in random order

Enables runtime switching of playback behavior without modifying client code.

### 🔹 Adapter Pattern

Device adapters wrap incompatible external device APIs into a unified interface:
- **BluetoothSpeakerAdapter**
- **WiredSpeakerAdapter**
- **HeadphonesAdapter**

Allows seamless integration of different device APIs through a common interface.

### 🔹 Factory Method Pattern

**DeviceFactory** encapsulates device creation logic, abstracting the instantiation process and promoting loose coupling between device creation and usage.

---

## 📂 Project Structure

```
MusicPlayerApplication/
│
├── main.cpp                      # Entry point and interactive CLI
├── MusicPlayerFacade.hpp         # High-level system interface
├── MusicPlayerApplication.hpp    # Application singleton
│
├── core/
│   └── AudioEngine.hpp           # Core playback logic
│
├── enums/
│   ├── DeviceType.hpp            # Audio device type enumeration
│   └── PlayStrategyType.hpp      # Playback strategy enumeration
│
├── models/
│   ├── Song.hpp                  # Song data model
│   └── Playlist.hpp              # Playlist data model
│
├── managers/
│   ├── PlaylistManager.hpp       # Manages playlists
│   ├── DeviceManager.hpp         # Manages audio devices
│   └── StrategyManager.hpp       # Manages playback strategies
│
├── strategies/
│   ├── PlayStrategy.hpp          # Abstract playback strategy
│   ├── SequentialPlayStrategy.hpp # Sequential playback implementation
│   └── RandomPlayStrategy.hpp    # Random playback implementation
│
├── device/
│   ├── IAudioOutputDevice.hpp    # Audio device interface
│   ├── BluetoothSpeakerAdapter.hpp
│   ├── WiredSpeakerAdapter.hpp
│   └── HeadphonesAdapter.hpp
│
├── external/
│   ├── BluetoothSpeakerAPI.hpp   # Mock external APIs
│   ├── HeadphonesAPI.hpp
│   └── WiredSpeakerAPI.hpp
│
└── factories/
    └── DeviceFactory.hpp         # Device creation factory
```

---

## 🛠️ Build & Run Instructions

### Prerequisites

- C++11 compatible compiler (e.g., g++)

### Build

```bash
cd "RhythmBox/C++ Code/MusicPlayerSystem/MusicPlayerApplication"
g++ -std=c++11 -o RhythmBox main.cpp
```

### Run

```bash
./RhythmBox
```

---

## 🧪 Sample Interactive Session

```
Initial song library populated with 5 songs.

===== RhythmBox Music Player =====
1.  Create Song in Library
2.  Create Playlist
3.  Add Song to Playlist
4.  Remove Song from Playlist
5.  Connect Device
6.  Set Playback Strategy
7.  Play Playlist
8.  Next Track
9.  Previous Track
10. View Playlists
11. Exit
==================================

Enter your choice: 2
Enter new playlist name: Road Trip Mix

Playlist "Road Trip Mix" created successfully.

===== RhythmBox Music Player =====
...
Enter your choice: 3
Enter playlist name: Road Trip Mix
Enter song title to add: Zinda

Song added to playlist successfully.

===== RhythmBox Music Player =====
...
Enter your choice: 5
Select a device:
1. Headphones
2. Bluetooth Speaker
3. Wired Speaker

Enter your choice: 2
Bluetooth Speaker connected.

===== RhythmBox Music Player =====
...
Enter your choice: 7
Enter playlist name to play: Road Trip Mix

-- Playing all tracks in 'Road Trip Mix' --
Playing song: Zinda
[BluetoothSpeaker] Playing: Zinda by Siddharth Mahadevan
Completed playlist: Road Trip Mix
```

---

## 💻 Technologies Used

- **Language**: C++11
- **Paradigm**: Object-Oriented Programming (OOP)
- **Principles**: SOLID Principles
- **Design Patterns**: Strategy, Singleton, Facade, Adapter, Factory Method
- **Interface**: Command-Line Interface (CLI)

---

## 🔮 Future Improvements

- Add persistent storage using file system or database
- Implement real-time playback with actual audio libraries
- Develop a GUI version using frameworks like Qt or ImGui
- Add comprehensive unit testing suite
- Introduce CMake build system
- Implement CI/CD pipeline (GitHub Actions)
- Add support for multiple audio formats
- Implement volume control and equalizer features

---

## 📜 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.