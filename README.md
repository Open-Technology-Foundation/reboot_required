
# System Reboot Scheduler

Bash script to set up a cron job to reboot the system if the uptime exceeds a specified number of days, or if the file `/var/run/reboot-required` exists.

It is designed for system administrators who want to ensure their systems are regularly rebooted for maintenance or security updates.

## Features

- Checks system uptime and schedules a reboot if it exceeds the specified threshold.
- Monitors the existence of `/var/run/reboot-required` to schedule a reboot.
- Flexible scheduling options for the reboot time and day.

## Prerequisites

- The script requires root or sudo privileges to create a cron job in `/etc/cron.d`.
- Bash environment (Debian/Ubuntu).

## Usage

1. Clone the repository or download the script.
2. Make the script executable:
    ```bash
    chmod +x reboot_required
    ```
3. Run the script with the desired parameters:
    ```bash
    reboot_required max_days [hour [min [dow]]]
    ```
    - `max_days`: The maximum number of days the system can be up before a reboot is scheduled.
    - `hour` (optional): The hour of the day when the reboot should occur (0-23). Default 1.
    - `min` (optional): The minute of the hour when the reboot should occur (0-59). Default 0.
    - `dow` (optional): The day of the week when the reboot should occur (Sun, Mon, ..., Sat, OR 0-7 where 0 or 7 is Sunday). Default is '\*' (any day).

## Example

To schedule a reboot if the system has been up for more than 7 days, or if `/var/run/reboot-required` exists, at 03:00 on Sunday:

```bash
sudo reboot_required 7 3 0 Sun
```

## Contributing

Contributions are welcome. Please open an issue or submit a pull request with your improvements.

(https://github.com/Open-Technology-Foundation/reboot_required)

## License

Distributed under the GPL3 License. See `LICENSE` for more information.

## Author

- Gary Dean, garydean@yatti.id

---

**Note:** This script is provided as-is without warranty. Please review the script before using it in a production environment.


