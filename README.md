# Hotel Management System (Java Swing)

A desktop application for managing hotel operations: rooms, check‑in/check‑out, payments, and user accounts.

Author: Vinayak — GitHub: https://github.com/vinayak746

## Features
- User authentication (Sign up, Login, Forgot password flow)
- Dashboard with quick navigation
- Room management (add/edit/view rooms)
- Guest Check‑In and Check‑Out (standard and “U” variants)
- Payments via Bkash and Nagad
- Profile management
- Visual room overview

## Tech Stack
- Java (JDK 8+)
- Swing/AWT for UI

## Project Structure
```
HotelManagementSystem/
├─ Main.java
├─ myClasses/               # GUI, business logic
│  ├─ Login.java
│  ├─ Signup.java
│  ├─ DashBoard.java
│  ├─ ManageRoom.java
│  ├─ ShowRoom.java
│  ├─ CheckIn.java
│  ├─ UCheckIn.java
│  ├─ CheckOut.java
│  ├─ UCheckOut.java
│  ├─ Payment.java
│  ├─ BkashPayment.java
│  ├─ NagadPayment.java
│  ├─ Profile.java
│  ├─ Edit.java
│  ├─ ForgetPass*.java
│  └─ UDashBoard.java
├─ myinterface/             # Interfaces (ConfirmPayment, etc.)
│  ├─ ConfirmPayment.java
│  ├─ ClearCheckOut.java
│  ├─ CheckOutRoomSearch.java
│  ├─ CustomerDataEntry.java
│  └─ WriteCheckInInfo.java
└─ out/                     # Compiled classes (generated)
```

## Prerequisites
- Install Java JDK 8 or newer
- Optional: Visual Studio Code with “Extension Pack for Java”

## Build and Run (Windows PowerShell)
From the project root:
```powershell
# Clean output folder
Remove-Item -Recurse -Force .\out -ErrorAction SilentlyContinue
New-Item -ItemType Directory -Path .\out | Out-Null

# Compile
javac -d out Main.java myClasses\*.java myinterface\*.java

# Run
java -cp out Main
```

## Running in VS Code
- Open the folder in VS Code.
- Ensure Java extensions are installed.
- Open Main.java and click “Run”.
- Or create a launch configuration with Main as the main class.

## Configuration Notes
- Packages:
  - Classes are under package `myClasses`.
  - Interfaces are under package `myinterface`.
- Ensure each interface file begins with:
  ```java
  package myinterface;
  ```
- If you rename folders, keep folder names matching package names (case-sensitive in Java code).

## Troubleshooting
- Error: “package myinterface does not exist”
  - Ensure the first line of each file in myinterface is `package myinterface;`
  - Compile including `myinterface\*.java` as shown above.

- Error: “method does not override or implement a method from a supertype”
  - Match method signatures exactly with the interface (name, parameters, return type).
  - Example: If `ConfirmPayment` declares `void confirmPayment(...)`, ensure implementing classes use the same signature.

- Error: “cannot find symbol ClearCheckOut.ClearCheckoutField”
  - Call static methods with the correct class/interface name and exact spelling/casing,
    or invoke instance methods on an object instance instead of a type.

- Mixed‑case folder/package issues
  - Windows file system is case‑insensitive, but Java packages are case‑sensitive.
  - Keep `myClasses` and `myinterface` consistent across folder names, package lines, and imports.

## Screenshots
Place screenshots in a `screenshots/` folder and reference them here:
- Login
- Dashboard
- Manage Rooms
- Check‑In / Check‑Out
- Payment
