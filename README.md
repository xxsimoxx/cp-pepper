# cp-pepper
ClassicPress Pepper for Passwords plugin releases repository.

## Notice
Source code for the plugin is in the [ClassicPress repository](https://github.com/ClassicPress/ClassicPress).
This repository holds the releases and it's used by the [ClassicPress Directory](https://directory.classicpress.net/) and the [ClassicPress directory Integration](https://directory.classicpress.net/plugins/classicpress-directory-integration/) plugin to serve updates.

# ClassicPress Pepper Password Plugin

## Overview

The **ClassicPress Pepper Password Plugin** is designed to enhance the security of user passwords gap in how password hashes are protected, by implementing a unique **pepper** mechanism.  WordPress and ClassicPress store **salts** in wp-config.php, which can be compromised if the site is breached.

This plugin allows administrators to generate and manage a pepper string that is used in conjunction with password hashing, adding an additional layer of protection against unauthorized access. This pepper - a secret value added to passwords before hashing - is stored separately **outside** the database.

It:
- Adds a secure pepper string managed independently.
- Automates pepper generation and refreshing.
- Requires using password resets when the pepper changes (users are not notified) - updates from previous hashing methods should be smoother.

## Why Use It?

- **Extra Layer of Security**  
  Even if an attacker gets your database and salts, they can't crack passwords without access to the external pepper file.

- **Low Maintenance**  
  The plugin quietly handles pepper generation and management, including a one-click refresh feature.

- **Great for Multi-User Sites**  
  Reduces damage from mass credential leaks in breach scenarios.

## When You Might Skip It

You might not need this plugin if:
- You're running a personal blog with no other users.
- You already have advanced server-level protections.
- You prioritize simplicity and minimal dependencies.

## Features

- **Pepper Generation**: Easily generate (or refresh) a random pepper string to enhance password security by clicking a button.
- **Settings Menu**: Access the plugin settings through the ClassicPress admin menu at **Settings > Pepper**.
- **Automatic Activation**: The plugin creates a pepper file upon activation, if it doesn't already exist, to store the random Pepper string.
- **User-Friendly Interface**: Simple navigation and clear messages for users.

## Manual Installation

1. Download the plugin .zip file.
2. Upload the `pepper-password` folder to the `/wp-content/plugins/` directory via FTP, or visiting **Plugins > Upload**.
3. Activate the plugin through the **Plugins** menu in ClassicPress.

## Installation

- Install the **ClassicPress Directory Integration** plugin and activate it on your site
- Visit **Plugins > Install CP Plugins** and search for **ClassicPress Pepper Password Plugin**
- You can install and activate the plugin by clicking the respective buttons.

## Usage

### Accessing Settings

- Navigate to **Settings > Pepper** in the ClassicPress admin dashboard to manage your pepper settings.

### Generating a Pepper

- Click on the **Enable Pepper** or **Renew Pepper** button within the settings page to generate or renew the pepper string.

### Important Notes

- Changing or deactivating this plugin will invalidate all stored password hashes, requiring users to reset their passwords.
- Ensure you have filesystem permissions set correctly for the plugin to function properly.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request for any enhancements or bug fixes.

## License

This plugin is licensed under the GPL v2 or later. Please see the LICENSE file for more details.

## Support

For support or inquiries, please open an issue in the repository or contact the plugin author directly.
