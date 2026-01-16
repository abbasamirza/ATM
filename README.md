# 🏧 ATM - Console-Based Banking System

A fully functional ATM simulation built in C that provides an interactive banking experience through a Windows console interface.  This student project demonstrates core banking operations with secure authentication and persistent data storage.

![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)

## 📋 Overview

This ATM system simulates real-world banking operations with a user-friendly console interface. It features user registration, secure PIN-based authentication, and essential banking transactions including withdrawals, balance management, and account operations.  All data is persistently stored in local files.

## ✨ Features

- **🔐 Secure Authentication**
  - NIC (National Identity Card) based user identification
  - 4-digit PIN code protection with masked input
  - PIN confirmation during registration

- **💰 Banking Operations**
  - Cash withdrawal with predefined amounts (500, 1000, 5000, 10000, 15000, 20000)
  - Custom withdrawal amounts (500-25,000 in multiples of 500)
  - Balance checking and display
  - Add funds to account
  - Real-time balance updates

- **👤 Account Management**
  - New user registration
  - Update PIN with validation
  - Delete account with PIN confirmation
  - Duplicate account prevention

- **🎨 Enhanced User Experience**
  - Color-coded console output (green for success, red for errors, blue for highlights)
  - Animated receipt displays
  - Maximized window for better visibility
  - Clear navigation menus

- **💾 Data Persistence**
  - File-based storage system
  - User data retained between sessions
  - Secure file handling with error checking

## 🚀 Getting Started

### Prerequisites

- Windows Operating System
- GCC compiler (MinGW) or any C compiler supporting Windows API
- Windows console with color support

### Compilation

```bash
gcc ATM.c -o ATM. exe
```

### Running the Application

```bash
ATM.exe
```

## 📖 Usage

### First Time Users (Registration)

1. **Launch the application** - The program displays a welcome screen
2. **Select option 2** - Choose "Register" from the main menu
3. **Enter NIC number** - Provide your National Identity Card number
4. **Create PIN** - Enter and confirm a 4-digit PIN code
5. **Enter name** - Provide your full name
6. **Set initial balance** - Enter the starting amount in your account
7. **Registration complete** - Your account is now created

### Existing Users (Login)

1. **Launch the application**
2. **Select option 1** - Choose "Login" from the main menu
3. **Enter NIC number** - Provide your registered NIC
4. **Enter PIN** - Input your 4-digit PIN code
5. **Access granted** - Main menu appears with available operations

### Main Menu Operations

Once logged in, you can perform the following operations:

#### 1️⃣ Cash Withdrawal
- Select from preset amounts or enter a custom amount
- Amount must be between 500 and 25,000
- Must be in multiples of 500
- Sufficient balance required
- Animated receipt displayed after successful withdrawal

#### 2️⃣ Update PIN
- Enter new 4-digit PIN
- Confirm new PIN
- Cannot use the same PIN as current
- Success message displayed

#### 3️⃣ Add Balance
- Enter amount to add to account
- Balance updated immediately
- Confirmation receipt displayed

#### 4️⃣ Delete Account
- Requires PIN confirmation
- Account permanently removed
- Returns to main screen

#### 0️⃣ Exit
- Log out and close application
- Thank you message displayed

## 🔄 Application Flow

```
┌─────────────────────────┐
│    Welcome Screen       │
│  1. Login               │
│  2. Register            │
│  0. Exit                │
└───────────┬─────────────┘
            │
     ┌──────┴──────┐
     ▼             ▼
┌─────────┐   ┌─────────┐
│  Login  │   │Register │
└────┬────┘   └────┬────┘
     │             │
     └──────┬──────┘
            ▼
    ┌───────────────┐
    │  Enter PIN    │
    └───────┬───────┘
            ▼
    ┌───────────────────┐
    │    Main Menu      │
    │ 1. Withdrawal     │
    │ 2. Update PIN     │
    │ 3. Add Balance    │
    │ 4. Delete Account │
    │ 0. Exit           │
    └───────────────────┘
```

## 🗂️ Data Structure

The application uses a struct to store user information:

```c
struct Users {
    char NAME[30];      // User's full name
    char NIC[14];       // National Identity Card number
    char PIN[5];        // 4-digit PIN code
    int BALANCE;        // Account balance
}
```

## 🔒 Security Features

- **PIN Masking**: PIN input is masked with asterisks (*)
- **Duplicate Prevention**: System checks for existing accounts before registration
- **Account Verification**: NIC-based authentication prevents unauthorized access
- **PIN Confirmation**: Double-entry verification during registration and updates
- **Balance Validation**: Prevents overdrafts and invalid transactions

## 📁 File Structure

```
ATM/
├── ATM.c           # Main source code
├── DATA.txt        # User data storage (auto-created)
├── TEMPDATA.txt    # Temporary file for updates (auto-created)
└── README.md       # Project documentation
```

## 🎯 Key Functions

| Function | Description |
|----------|-------------|
| `maximize_window()` | Maximizes console window for better display |
| `print_welcome()` | Displays welcome banner with colored text |
| `login()` | Handles user authentication |
| `signup()` | Manages new user registration |
| `withdraw()` | Processes cash withdrawal transactions |
| `update_PIN()` | Changes user PIN with validation |
| `add_BALANCE()` | Adds funds to user account |
| `delete_account()` | Removes user account from system |
| `print_reciept()` | Displays animated transaction receipts |

## ⚠️ Limitations

- Windows-only (uses Windows. h API)
- File-based storage (not encrypted)
- No network connectivity
- Maximum withdrawal:  25,000 per transaction
- PIN limited to numeric characters only

## 🎓 Learning Outcomes

This project demonstrates:
- File I/O operations in C
- Struct-based data management
- Windows console API usage
- Input validation and error handling
- User authentication implementation
- Menu-driven program design
- Data persistence techniques

## 🤝 Contributing

This is a student project.  Feel free to fork and enhance with features like:
- Database integration
- Transaction history
- Multiple currency support
- Receipt printing
- Account statements
- Transfer between accounts

## 📝 License

This project is open source and available for educational purposes.

---

<p align="center">
  <strong>Made with ❤️ for learning C programming</strong>
</p>
