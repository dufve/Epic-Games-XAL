# Epic-Games-XAL
Repository for reverse-enginerring the Epic Games Talon SDK to generate XAL fingeprint values.

## The mission:
The current Talon_SDK.js file is nearly `50 000` lines long after being deobfuscated. However, 99% of the logic in the file is not necessary for the calculation of the XAL fingerprint value of the user.

The scope of this project is to reverse-engineer the Talon SDK and create a standalone JavaScript file that can emulate the XAL value calculation of the Talon SDK. This involves moving backwards in the logic of the XAL calculation, which is defined by the function "`_0x5362f5`" with "`_0x2ba0ad`" as an argument.

**What does it fingerprint? (Thank you infect01 for this chart)**

| Browser Properties | WebGL Properties    | Screen Properties    | Date Properties    | FingerprintJS Properties    | Motion Events   | 
| :---:   | :---: | :---: | :---: | :---: | :---: |
| User-Agent | Canvas   | Width   | Timezone Offset | Visitor ID (Hash) | Mouse Movements (Timestamp, X Position, Y Position)
| Webdriver | Graphics Card   | Height   | Timezone | Confidence | Mouse Up (Timestamp, X Position, Y Position)
| N/A | N/A | N/A | N/A | Fonts (Hash) | Mouse Down (Timestamp, X Position, Y Position) |
| N/A | N/A | N/A | N/A | Plugins (Hash) | Touch Events (for mobile) |
| N/A | N/A | N/A | N/A | Audio (Hash) | Keyboard Up (Timestamp)  |
| N/A | N/A | N/A  | N/A | Canvas (Hash) | Keyboard Down (Timestamp) |
| N/A | N/A | N/A | N/A | Screen (Hash) | Resize Events - if you resized the browser window (Timestamp, Width, Height) |

## Curent constants:

fingerprint_version: `30`

xorCipherKey (_0x2fb187): ``\x030é\b7\xB0\x94\x0E-\xB3x\x9DûËfîâÀ\x0EZâ\xA9\x04\x9CSÑä`\x88\x9CÁ\'``

ewa: `b`

kid: `p98hck`

## TODO (in order of importance):
- Completely reverse XAL calculation flow
- Rename all variables and functions from HEX names (by-product from the de-obfuscation) to meaningful and readable names.
- Create script to decode and encode XAL value using a XOR cipher.
- Optimize codebase as it is still quite cluttered (by-product from the de-obfuscation).
