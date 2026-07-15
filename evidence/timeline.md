# Attack Timeline

| Phase | Description                              |
| ----- | ---------------------------------------- |
| 1     | SSH service discovered using Nmap        |
| 2     | Password list created                    |
| 3     | Hydra launched against SSH               |
| 4     | Five failed authentication attempts      |
| 5     | Successful SSH login                     |
| 6     | User and system enumeration              |
| 7     | Attempted access to privileged resources |
| 8     | Permission denied for `/root`            |
| 9     | Permission denied for `/etc/shadow`      |
| 10    | SSH session terminated                   |
| 11    | Authentication logs analyzed             |
| 12    | Digital evidence collected               |

