# Parent Assignment Local Plugin

## Description
This Moodle local plugin automatically assigns a "Parent" role to a user based on custom profile fields (`parent_email`, `parent_name`) in the student's account. If the parent account does not exist, it is automatically created.

## Requirements
*   Moodle 4.1 or later.
*   Custom User Profile Fields:
    *   `parent_email` (Text input)
    *   `parent_name` (Text input)
*   A Role with the shortname `parent` (or configured otherwise in code).

## Installation
1.  Copy the `local_parentassign` directory to the `local/` directory of your Moodle installation.
2.  Visit **Site administration > Notifications** to trigger the installation.
3.  Ensure the required custom profile fields and role exist.

## Usage
The plugin works automatically in two ways:
1.  **Event-based**: When a user is created or updated, if the `parent_email` field is set, the assignment logic runs immediately.
2.  **Scheduled Task**: A background task (`\local_parentassign\task\process_parents`) runs periodically to process users who may have been missed or updated in bulk.

## Privacy
This plugin does not store any personal data. It processes existing user data to facilitate role assignments.

## License
[GNU GPL v3 or later](http://www.gnu.org/copyleft/gpl.html)
