# Integrated Forms for WooCommerce
A WordPress and WooCommerce Plugin to Print Integrated Forms
By incube.co

# Abstract
This is a WordPress plugin that works with WooCommerce to allow the user to create an integrated form (Packing slip & Mailing Label).

The will allow the user to *create* the look and feel of the form by creating *sections* (such as a heading, logo, item, etc) and placing it on the PDF template using x and y coordinates (in mm).

One of the *sections* will be the mailer (which is typically a 4x6" label provided as a PDF file).

# Contents
Below are the the ideas, implementations as available, and "to do" lists.

## WordPress Plugin Setup and Pre-Checks
Each WordPress Plugin requires a header that defines it.
```
/**
 * Plugin Name: Integrated Forms for WooCommerce
 * Plugin URI: https://incube.co
 * Description: A WooCommerce Plugin to Print Integrated Forms by incube.co
 * Version: 0.1.0
 * Author: incube.co
 * Author URI: https://incube.co
 * Text Domain: incube-integratedforms
 *
 * @package Incube-IntegratedForms
 */
```
The plugin should also verify that it is not being directly accessed for safety.
```
if ( ! defined( 'ABSPATH' ) ) {
     exit; // Exit if accessed directly
}
```
The plugin will also verify that WooCommerce is installed/active to actually do anything.
```
if ( in_array( 'woocommerce/woocommerce.php', apply_filters( 'active_plugins', get_option( 'active_plugins' ) ) ) ){
  // The Plugin Code
}
```

## The ADMIN Order Section
On this screen we want to Add a Column that shows the "Status" of the Integrated Form for that particular order. 
The States include:
- Not Created
- Created
- Printed
These will be done with bootstrap CSS.

### Hooking into the WordPress/WooCommerce functionality
To insert your functionality into WordPress and WooCommerce, you define your function and add it as an action to be run when a particular section of code is reached.  These are called Actions and Filters.

## The Integrated Forms ADMIN Page
