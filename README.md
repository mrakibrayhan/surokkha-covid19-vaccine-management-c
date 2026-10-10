# SUROKKHA — COVID-19 Vaccine Management System

A console-based COVID-19 vaccine registration and management system written in C. Named after Bangladesh's national vaccine registration initiative, the system allows citizens to register for vaccination, check their registration status, and correct their details, while administrators can view all registrations and update vaccination records.

## Features

**Vaccine Registration**
- Register a new patient (name, age, gender, 7-digit NID, username, password)
- Enforces a minimum registration age (currently 18)
- Enforces a strict 7-digit NID format

**User Menu**
- **Registration Status** — view your own registration details
- **Correction** — update your name, age, gender, or NID after verifying your NID + username/password (limited to 3 attempts)

**Admin Menu** (protected by admin login)
- View all registered patients
- View all registrations filtered by vaccine given
- Update a patient's vaccine name and dose number

**Hotline**
- Displays official COVID-19 helpline numbers (National Call Center, Health Portal, IEDCR, Telehealth)

## Tech Stack

- **Language:** C
- **Data storage:** In-memory array of structs (`struct data person[500]`) — data is not persisted to disk or a database; all records are lost when the program exits

## Build & Run

```bash
gcc surokkha.c -o surokkha
./surokkha
```

> **Note:** This program uses `gets()`, `fflush(stdin)`, and `getch()`, which are non-standard or deprecated and primarily supported by older/Windows-oriented compilers (e.g. Turbo C, or GCC with `conio.h` support via MinGW). On modern GCC/Clang on Linux or macOS, `gets()` is not available and `getch()`/`conio.h` do not exist, so the program will need adjustments (e.g. replacing `gets()` with `fgets()`, and `getch()` with `getchar()`) to compile cleanly.

## Default Admin Login

- **Username:** `admin`
- **Password:** `adminpass`

> Credentials are hardcoded for demo purposes — this is an academic project, not intended for real-world deployment.

## Known Limitations

- No data persistence — all registrations exist only for the current run
- Passwords are stored and compared in plain text
- Fixed-size record array (max 500 patients)
- Uses deprecated/unsafe C functions (`gets()`) which can cause buffer overflows

## Developers

- Rakib Rayhan
- Md. Shakhawat Hossain
- Sadia Afra Ibnat
- Usuf Amin

## Project Type

Academic C programming project demonstrating structs, arrays, string handling, and menu-driven console program design.
