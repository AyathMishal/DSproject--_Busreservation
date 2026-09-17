# Bus Reservation System

A menu-driven bus reservation system written in C. The program runs in a terminal and lets an authenticated user view available routes, reserve seats, cancel bookings, inspect seat availability, and look up reservation details.

## Features

- Login screen before accessing the reservation menu
- Display nine bus routes with destinations, fares, and departure times
- Book one or more seats on a selected bus
- Generate customer IDs from the bus and seat numbers
- Display the availability of all 32 seats on a bus
- Cancel seats using the generated reservation number
- View reservation details, including passenger name, bus number, seat number, and ticket cost
- Store reservations in a binary search tree while the program is running
- Color-coded terminal output for status and validation messages

## Technology

- C
- Standard C libraries
- `conio.h` for password input without echoing characters
- Binary search tree for reservation lookup

## Project files

| File | Description |
| --- | --- |
| `BusReservation.c` | Application source code |
| `BusReservation.exe` | Windows executable included with the project |
| `.vscode/` | Visual Studio Code launch configuration |

## Login

The current source code uses the following password:

```text
password
```

The username is requested by the program, but the current implementation does not validate it. Change the credentials in `BusReservation.c` before using this project in a real system.

## Build and run

### Using GCC on Windows

Install a C compiler such as MinGW-w64, then run these commands from the project directory:

```bash
gcc BusReservation.c -o BusReservation.exe
BusReservation.exe
```

The program uses `conio.h` and is intended for Windows-compatible C environments. The included executable can also be launched directly:

```text
BusReservation.exe
```

### Using Visual Studio Code

Open the project folder in Visual Studio Code and build `BusReservation.c` with a configured C/C++ compiler. The `.vscode` directory contains the existing launch configuration for the project.

## Using the application

After logging in, choose an option from the main menu:

1. **View bus list** - Show routes, fares, and departure times.
2. **Book tickets** - Select a bus and one or more available seats.
3. **Cancel booking** - Enter the reservation number and cancel selected seats.
4. **Buses seats info** - Check which seats are empty or booked.
5. **Reservation info** - Use a reservation number and customer ID to view ticket details.
6. **Exit** - Close the application.

Each bus has 32 seats. Customer IDs are generated using the following format:

```text
bus number × 1000 + seat number
```

For example, seat 12 on bus 3 produces customer ID `3012`.

## Important notes

- Reservations are kept in memory and are lost when the program exits.
- The program currently does not prevent booking a seat that is already marked as booked.
- Passenger names are read into a fixed-size buffer; use short names.
- The included `.exe` is a Windows build and may not run on other operating systems.
- Review and update the hard-coded routes, fares, credentials, and validation rules before deploying the project.

## License

No license has been specified for this project. Add a license file before distributing it publicly.
