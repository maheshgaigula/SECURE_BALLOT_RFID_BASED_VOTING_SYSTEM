\# 🔐 Secure Ballot – RFID-Based Electronic Voting System



An \*\*RFID-Based Electronic Voting System\*\* developed using the \*\*LPC2148 ARM7 microcontroller\*\* to provide a secure, reliable, and user-friendly electronic voting process.



The system uses \*\*RFID authentication, password protection, EEPROM-based voter validation, RTC timing, LCD display, and keypad input\*\* to control the complete voting process.



\---



\## 📸 Project Screenshots



\### 🔧 Hardware Setup



!\[RFID Voting System Hardware](major\_images/hardware\_setup.jpeg)



\### 📟 LCD \& Keypad Interface



!\[LCD and Keypad Interface](major\_images/lcd\_keypad\_interface.jpeg)



\### 🧾 Serial Audit Log



!\[Serial Audit Log](major\_images/serial\_audit\_log.jpeg)



\### 🏆 Election Result



!\[Election Result](major\_images/election\_result.jpeg)



\---



\## 📌 Project Overview



The \*\*Secure Ballot\*\* system is an embedded electronic voting solution designed using the \*\*LPC2148 ARM7 microcontroller\*\*.



The system provides separate \*\*administrator and voter interfaces\*\*. The administrator can configure the election, while voters are authenticated using RFID cards before casting their votes.



The system also uses an \*\*RTC for controlling the election time period\*\* and \*\*EEPROM for storing voter validation information and voting status\*\*.



\---



\## 🎯 Objectives



\- Provide secure voter authentication using RFID.

\- Prevent unauthorized voting.

\- Prevent duplicate voting.

\- Provide administrator authentication using RFID and password.

\- Control the election using a predefined start and end time.

\- Store voter validation information in EEPROM.

\- Display system information through an LCD.

\- Provide a simple keypad-based user interface.

\- Monitor important system events through UART serial communication.



\---



\## 👨‍💼 Administrator Operations



The administrator can perform the following operations:



\- Admin RFID authentication

\- Password authentication

\- Configure voting start time

\- Configure voting end time

\- Change administrator password

\- View election results

\- Announce election results

\- Monitor system information through UART

\- Lock the system after multiple incorrect password attempts



\---



\## 🗳️ Voter Operations



The voter can:



1\. Present the RFID card.

2\. System reads the RFID card through the EM-18 RFID reader.

3\. RFID data is validated.

4\. System checks whether the voter has already voted.

5\. Valid voters are allowed to continue.

6\. Voter selects the preferred candidate using the keypad.

7\. Vote is recorded.

8\. Voter status is updated to prevent duplicate voting.



\---



\## ⭐ Key Features



\- 🔐 RFID-based authentication

\- 🔑 Password-protected administrator interface

\- 🕐 RTC-based election timing

\- 💾 EEPROM-based voter validation

\- 🚫 Duplicate-vote prevention

\- 🔒 Failed password attempt lock

\- 📟 20×4 LCD interface

\- ⌨️ 4×4 matrix keypad

\- 📡 EM-18 RFID reader

\- 🔌 UART serial communication

\- 💡 LED status indication

\- 📊 Election result management



\---



\## 🧰 Hardware Components



| Component | Purpose |

|---|---|

| LPC2148 ARM7 | Main microcontroller |

| EM-18 RFID Reader | RFID card identification |

| 20×4 LCD | Display system information |

| 4×4 Keypad | User input |

| RTC | Election timing |

| I2C EEPROM | Voter data and voting status |

| MAX232 / USB-Serial | PC serial communication |

| LEDs | Status indication |

| Power Supply | System power |



\---



\## 💻 Software \& Development Tools



\- Embedded C

\- Keil µVision

\- Flash Magic

\- Proteus

\- HyperTerminal

\- ARM7 LPC2148

\- UART

\- I2C

\- GPIO

\- RTC

\- EEPROM



\---



\## 🏗️ System Architecture



```text

&#x20;                   +----------------------+

&#x20;                   |      LPC2148         |

&#x20;                   |      ARM7 MCU        |

&#x20;                   +----------+-----------+

&#x20;                              |

&#x20;      +-----------------------+-----------------------+

&#x20;      |                       |                       |

&#x20;      v                       v                       v

+-------------+         +-------------+         +-------------+

|   EM-18     |         |    LCD      |         |   Keypad    |

| RFID Reader |         |   20×4      |         |    4×4      |

+-------------+         +-------------+         +-------------+

&#x20;      |

&#x20;      v

+-------------+

|    UART1    |

+-------------+



&#x20;      +-----------------------+

&#x20;      |                       |

&#x20;      v                       v

+-------------+         +-------------+

| I2C EEPROM  |         |     RTC     |

| Voter Data  |         | Election    |

| \& Status    |         | Timing      |

+-------------+         +-------------+

```



\---



\## ⚙️ System Working



\### 1. Administrator Authentication



The administrator first scans the authorized RFID card.



The system then requests the administrator password.



If the credentials are correct, the administrator menu is displayed.



After multiple incorrect password attempts, the system locks the administrator interface.



\### 2. Election Configuration



The administrator can configure:



\- Voting start time

\- Voting end time

\- Administrator password



The RTC is used to control the configured election period.



\### 3. Voter Authentication



The voter scans an RFID card using the EM-18 RFID reader.



The RFID reader communicates with the LPC2148 through \*\*UART1\*\*.



The system validates the received RFID information.



\### 4. Duplicate Vote Prevention



The system checks the voter's status stored in EEPROM.



If the voter has already voted, the system rejects the voting attempt.



If the voter is valid and has not voted, the system allows voting.



\### 5. Vote Casting



The voter selects a candidate using the keypad.



For example:



```text

1 → Party A

2 → Party B

3 → Party C

```



The selected vote is recorded by the system.



\### 6. Election Result



After the election, the administrator can view and announce the results.



The candidate vote counts are displayed through the LCD interface.



\---



\## 🕐 RTC-Based Voting Control



The RTC is used to control the election period.



The system checks the current RTC time against the configured:



```text

Voting Start Time

&#x20;       ↓

Voting Period

&#x20;       ↓

Voting End Time

```



Voting is allowed only during the configured election period.



\---



\## 📟 LCD Interface



The \*\*20×4 LCD\*\* provides information such as:



\- Administrator menu

\- Password input

\- RFID authentication status

\- Voting status

\- Candidate selection

\- Election timing

\- Result information

\- Error messages



\---



\## ⌨️ Keypad Interface



A \*\*4×4 matrix keypad\*\* is used for:



\- Administrator menu navigation

\- Password entry

\- Election time configuration

\- Candidate selection

\- System commands



\---



\## 📡 RFID Communication



The project uses an \*\*EM-18 RFID reader\*\* for card identification.



The EM-18 reader communicates with the LPC2148 through \*\*UART1\*\*.



The RFID frame used by the system follows the format:



```text

0x02 + RFID Data + 0x03

```



The received RFID information is processed by the microcontroller for authentication and voter validation.



\---



\## 🔌 UART Serial Monitoring



UART communication is also used for monitoring system information through a PC.



Typical configuration:



```text

Baud Rate : 9600

Data Bits : 8

Parity    : None

Stop Bits : 1

```



Serial monitoring helps during development and debugging.



\---



\## 🔗 Main Hardware Interfaces



| Interface | Connected Device |

|---|---|

| UART1 | EM-18 RFID Reader |

| I2C | EEPROM |

| RTC Interface | Real-Time Clock |

| GPIO | LCD |

| GPIO | 4×4 Keypad |

| GPIO | LEDs |

| UART | PC Serial Monitoring |



\---



\## 🧩 Main Software Modules



The project is divided into multiple Embedded C modules:



```text

main.c

UART.c

UART1.c

I2C.c

I2c\_Eeprom.c

RTC\_Defaults.c

KPM.c

lcd.c

Password.c

Officer\_interface.c

Voter\_Interface.c

DATA.c

Check.c

delay.c

My\_Str\_Func.c

```



Header files are used to maintain modularity and provide required definitions and function declarations.



\---



\## 📁 Project Structure



```text

SECURE\_BALLOT\_RFID\_BASED\_VOTING\_SYSTEM/

│

├── major\_images/

│   ├── hardware\_setup.jpeg

│   ├── lcd\_keypad\_interface.jpeg

│   ├── serial\_audit\_log.jpeg

│   └── election\_result.jpeg

│

├── main.c

├── UART.c

├── UART1.c

├── I2C.c

├── I2c\_Eeprom.c

├── RTC\_Defaults.c

├── KPM.c

├── lcd.c

├── Password.c

├── Officer\_interface.c

├── Voter\_Interface.c

├── DATA.c

├── Check.c

├── delay.c

├── My\_Str\_Func.c

│

├── project\_files.uvproj

├── project\_files.uvopt

├── major\_project.hex

└── README.md

```



\---



\## 🧪 Testing \& Debugging



The system was tested for different operating conditions including:



\- Valid administrator RFID

\- Invalid administrator RFID

\- Correct password

\- Incorrect password

\- Multiple incorrect password attempts

\- Valid voter RFID

\- Invalid voter RFID

\- Already-voted voter

\- Voting outside the configured election period

\- Candidate selection

\- Election result display

\- UART serial monitoring



\---



\## 🧠 Embedded Concepts Demonstrated



This project demonstrates practical knowledge of:



\- Embedded C programming

\- ARM7 LPC2148 microcontroller

\- UART communication

\- RFID interfacing

\- I2C communication

\- EEPROM interfacing

\- RTC interfacing

\- LCD interfacing

\- Matrix keypad interfacing

\- GPIO programming

\- Modular firmware development

\- Hardware-software interfacing

\- Debugging using serial communication



\---



\## 🌍 Applications



The concept can be adapted for:



\- Small-scale electronic voting systems

\- Institutional elections

\- College elections

\- Organization-level voting

\- Secure polling prototypes

\- Embedded authentication systems



\---



\## 📚 Learning Outcomes



Through this project, I gained practical experience in:



\- Developing Embedded C firmware

\- Working with LPC2148 ARM7

\- Interfacing RFID readers

\- Implementing UART communication

\- Interfacing EEPROM using I2C

\- Working with RTC modules

\- Designing LCD and keypad interfaces

\- Implementing authentication mechanisms

\- Debugging embedded systems

\- Developing modular embedded applications



\---



\## 🚀 Project Highlights



\- \*\*Microcontroller:\*\* LPC2148 ARM7

\- \*\*Programming Language:\*\* Embedded C

\- \*\*RFID Reader:\*\* EM-18

\- \*\*RFID Interface:\*\* UART1

\- \*\*Display:\*\* 20×4 LCD

\- \*\*Input:\*\* 4×4 Matrix Keypad

\- \*\*Memory:\*\* I2C EEPROM

\- \*\*Timing:\*\* RTC

\- \*\*Serial Monitoring:\*\* UART

\- \*\*Development Environment:\*\* Keil µVision



\---



\## 🔄 Overall Project Workflow



```text

&#x20;         START

&#x20;           |

&#x20;           v

&#x20;  Administrator Login

&#x20;           |

&#x20;     RFID + Password

&#x20;           |

&#x20;           v

&#x20;   Configure Election

&#x20;           |

&#x20;  Start Time / End Time

&#x20;           |

&#x20;           v

&#x20;     Voting Period

&#x20;           |

&#x20;           v

&#x20;      Scan RFID

&#x20;           |

&#x20;           v

&#x20;   Validate Voter

&#x20;           |

&#x20;     +-----+-----+

&#x20;     |           |

&#x20;  Invalid       Valid

&#x20;     |           |

&#x20;     v           v

&#x20;   Reject    Check Voting

&#x20;                Status

&#x20;                  |

&#x20;            +-----+-----+

&#x20;            |           |

&#x20;         Already      Not Voted

&#x20;          Voted          |

&#x20;            |            v

&#x20;            v       Select Candidate

&#x20;          Reject          |

&#x20;                          v

&#x20;                     Record Vote

&#x20;                          |

&#x20;                          v

&#x20;                   Update Voter Status

&#x20;                          |

&#x20;                          v

&#x20;                    Election Result

&#x20;                          |

&#x20;                          v

&#x20;                         END

```



\---



\## 👨‍💻 Author



\*\*Gaigula Mahesh\*\*



Electronics and Communication Engineering



Interested in \*\*Embedded Software, Firmware Development, and Embedded Systems\*\*.



\---



\## 📄 License



This project is intended for \*\*educational and demonstration purposes\*\*.



\---



\## ⭐ Project Summary



\*\*Secure Ballot\*\* demonstrates how an ARM7-based embedded system can combine \*\*RFID authentication, password protection, EEPROM data storage, RTC-based timing, LCD/keypad interfaces, and UART communication\*\* to build a secure electronic voting prototype.



The project provides practical exposure to \*\*Embedded C programming, microcontroller peripherals, hardware interfacing, firmware development, and embedded system debugging\*\*.

