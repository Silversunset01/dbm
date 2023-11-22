# Timestamps 

| Task | Script | Output |
| :--- | :--- | :---
| Get current date for discord timestamp | `Math.floor(new Date().getTime() / 1000)` | 
| Use current date in discord timestamp | `<t:${Math.floor(new Date().getTime() / 1000)}:t>` | 12:00 PM
| Use current date in discord timestamp | `<t:${Math.floor(new Date().getTime() / 1000)}:T>` | 12:00:00 PM
| Use current date in discord timestamp | `<t:${Math.floor(new Date().getTime() / 1000)}:d>` | 12/01/2023
| Use current date in discord timestamp | `<t:${Math.floor(new Date().getTime() / 1000)}:D>` | December 1, 2023
| Use current date in discord timestamp | `<t:${Math.floor(new Date().getTime() / 1000)}:f>` | December 1, 2023 12:00 PM
| Use current date in discord timestamp | `<t:${Math.floor(new Date().getTime() / 1000)}:F>` | Friday, December 1, 2023 12:00 PM
| Use current date in discord timestamp | `<t:${Math.floor(new Date().getTime() / 1000)}:R>` | 1 year ago
