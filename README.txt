Commerce Order Phone QR
========================

Drupal 7 module that adds a QR code for the shipping phone number in the Commerce order quick edit section.

DESCRIPTION
-----------

This module automatically generates and displays a QR code for the shipping phone number when viewing orders in the Commerce Backoffice quick edit section. The QR code appears directly under the phone field in the shipping information section, making it easy to scan and use the phone number.

REQUIREMENTS
------------

- Drupal 7.x
- Commerce module
- Commerce Customer module
- Commerce Backoffice Order module
- phpqrcode library (see installation instructions)

IMPORTANT: Field Name Requirement
----------------------------------

This module requires that your shipping customer profile has a phone field named **`field_telefon`**.

If your phone field has a different name, you will need to either:
- Rename your field to `field_telefon`, or
- Modify the module code to use your field name

INSTALLATION
------------

1. Download and extract this module to `sites/all/modules/` (or your custom modules directory)

2. Download the phpqrcode library:
   - Go to: https://sourceforge.net/projects/phpqrcode/
   - Download the latest version
   - Extract to: `sites/all/libraries/phpqrcode/`
   - Ensure the file `qrlib.php` exists in that directory

3. Enable the module:
   - Navigate to `admin/modules`
   - Find "Commerce Order Phone QR" under "Epectasys" package
   - Enable the module
   - Clear Drupal cache

4. Verify your shipping profile has the `field_telefon` field:
   - Go to `admin/commerce/customer-profiles/types/shipping/fields`
   - Ensure a field named `field_telefon` exists
   - If not, create it or rename your existing phone field

USAGE
-----

1. Navigate to `admin/commerce/orders`
2. Click "Quick edit" on any order
3. In the shipping information section, you will see:
   - The phone number field (Telefon)
   - A QR code image below it (if phone number exists)
4. Scan the QR code with any QR code reader to get the phone number

FEATURES
--------

- Automatically displays QR code for shipping phone numbers
- QR code appears under the "Telefon" field in shipping information
- QR code is generated on-the-fly as a base64 data URI (no file storage needed)
- Only displays if a phone number exists in the shipping profile
- Only shows for shipping profiles (not billing profiles)
- Works in both administrator and backoffice view modes

TROUBLESHOOTING
---------------

**QR code doesn't appear:**
- Verify the shipping profile has a phone number in `field_telefon`
- Check that the phpqrcode library is installed correctly
- Check watchdog logs for any errors
- Clear Drupal cache

**Library not found error:**
- Ensure phpqrcode library is in `sites/all/libraries/phpqrcode/`
- Verify `qrlib.php` exists in that directory
- Check file permissions

**Module doesn't appear in modules list:**
- Verify the module is in the correct directory
- Check the `.info` file is named correctly
- Clear Drupal cache

LICENSE
-------

See LICENSE file for details.

SUPPORT
-------

For issues, feature requests, or contributions, please use the GitHub issue tracker.

AUTHOR
------

Created for Drupal Commerce sites requiring QR code display for shipping phone numbers.

