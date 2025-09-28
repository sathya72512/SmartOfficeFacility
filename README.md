# Smart Office Facility Management System

## 📌 Overview

This project is a **Smart Office Facility Management System** implemented in Java.
It demonstrates the use of **design patterns** such as **Singleton**, **Observer**, and **Command**, along with an **auto-release feature** for meeting rooms.

The system allows users to interact through a console with commands to book rooms, cancel bookings, add/remove occupants, and exit.

---

## 🛠️ Features

* **Singleton**:
  `OfficeManager` ensures only one instance manages all rooms.

* **Observer**:
  When occupants enter or leave, `Room` notifies `ACController` and `LightController` to switch ON/OFF automatically.

* **Command Pattern**:
  User actions (`book`, `cancel`, `add`, `remove`) are implemented as separate command classes (`BookRoomCommand`, `CancelRoomCommand`, etc.).

* **Auto Release**:
  If a room is booked but remains empty for 10 seconds (demo; in real system 5 minutes), it is automatically released.

* **Exception Handling**:
  Invalid room IDs throw a custom exception (`InvalidRoomException`).

* **Interactive Console**:
  User can type commands like:

  ```
  book <roomId>
  cancel <roomId>
  add <roomId> <count>
  remove <roomId>
  exit
  ```

---

## ▶️ Example Run

```
Office configured with 2 rooms.
=== Smart Office Facility ===
Commands:
 book <roomId>
 cancel <roomId>
 add <roomId> <count>
 remove <roomId>
 exit

> book 1
Room 1 booked successfully.

> add 1 2
Room 1 now has 2 occupants.
[AC Controller] Room 1 -> AC and Lights turned ON.
[Light Controller] Room 1 -> AC and Lights turned ON.

> remove 1
Room 1 is now empty.
[AC Controller] Room 1 -> AC and Lights turned OFF.
[Light Controller] Room 1 -> AC and Lights turned OFF.

> cancel 1
Booking for Room 1 cancelled.

> book 2
Room 2 booked successfully.
(wait 10 seconds...)
Room 2 auto-released (no occupants).

> book 3
Invalid room id: 3
```

---

## ⚙️ Requirements

* Java 8 or above
* Eclipse/IntelliJ or any Java IDE

---

## 🚀 How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/<YourUsername>/SmartOfficeFacility.git
   ```
2. Open in Eclipse/IntelliJ.
3. Run `Main.java`.
4. Type commands in the console to interact with the system.

---


✅ This project was developed as part of an **interview problem-solving task**.
