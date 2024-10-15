# SnapDialog Plugin Documentation

## Overview
SnapDialog is a versatile JavaScript plugin offering customizable prompt boxes and notification dialog alerts. Capture user input or deliver dynamic notifications with ease. Its intuitive API and flexible options ensure smooth integration, enhancing user interaction while combining simplicity with power.

## Features
- **Customizable notification types**: `success`, `error`, `warning`, `info`, `html`
- **Input field support**: Allows input within dialogs
- **Progress bar support**: Option to include a progress bar that tracks the duration before auto-close
- **RTL support**: Right-to-left text support
- **Dark mode**: Option to toggle between light and dark modes
- **Sizing options**: Multiple Size for displaying dialog
- **Animation options**: Various animations for notification appearance
- **Event handlers**: Custom actions for confirm, cancel, and close events
- **Custom icons**: Ability to define custom icons for each notification type

## Installation

Here's how to use SnapDialog in your project:

### Installation via CSS

Include the stylesheet on your document's <head>  `</head>` tag.

```html
<head>
  <link rel="stylesheet" href="snap-dialog.css">
  <!-- Or -->
  <link rel="stylesheet" href="snap-dialog.min.css">
</head>
```

Instead of installing you may use the remote version.

```html
<head>
  <link rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/snap-dialog-js@latest/dist/snap-dialog.css">
  <!-- Or -->
  <link rel="stylesheet"
  href="https://unpkg.com/snap-dialog-js@latest/dist/snap-dialog.min.css">
</head>
```

### Installation via Javscript

Include the Plugin on your document's  before `</body>` tag.

```html
  <script src="/snap-dialog.js"></script>
  <!-- Or -->
  <script src="/snap-dialog.min.js"></script>
```

Instead of installing you may use the remote version.

```html
  <script src="https://cdn.jsdelivr.net/npm/snap-dialog-js@latest/dist/snap-dialog.js"></script>
  <!-- Or -->
  <script src="https://unpkg.com/snap-dialog-js@latest/dist/snap-dialog.min.js"></script>
```
`

## Usage

### Basic Notification
```javascript
SnapDialog().success('Success Title', 'This is a success message.');
```

### Error Notification
```javascript
SnapDialog().error('Error Title', 'This is an error message.');
```

### Info Notification
```javascript
SnapDialog().info('Info Title', 'This is an information message.');
```

### Warning Notification
```javascript
SnapDialog().warning('Warning Title', 'This is a warning message.');
```

### Custom HTML Content
```javascript
SnapDialog().html('<div><h3>Custom HTML</h3><p>This is a custom HTML dialog.</p></div>');
```

### Configuring Options
You can configure global options for the plugin:
```javascript
SnapDialog().SnapDialogOptions({
    rtl: true,
    isDark: true,
    autoClose : true,
    duration: 5000
});
```

### Confirm and Cancel Example
You can handle confirm and cancel actions within a dialog:
```javascript
SnapDialog().alert('Confirm Action', 'Are you sure?', {
    enableConfirm: true,
    onConfirm: function() {
        console.log('Confirmed');
    },
    enableCancel: true,
    onCancel: function() {
        console.log('Cancelled');
    }
});
```

### Custom Input
You can create dialogs that include input fields:
```javascript
SnapDialog().alert('Input Dialog', 'Please enter your name:', {
    input: 'text',
    inputPlcaeholder: 'Your name',
    enableConfirm: true,
    onConfirm: function(inputValue) {
        console.log('Input value:', inputValue);
    }
});
```

### Clear All Notifications
```javascript
SnapDialog().clearAll();
```

## Available Options
| Option             | Type      | Default        | Description                                                 |
|--------------------|-----------|----------------|-------------------------------------------------------------|
| `rtl`              | `boolean` | `false`        | Enables right-to-left text alignment.                        |
| `type`             | `string`  | `null`         | Notification type (`success`, `error`, `warning`, `info`).   |
| `title`            | `string`  | `'Default Title'` | Title for the notification.                                  |
| `message`          | `string`  | `'This is a default message'` | Message for the notification.                               |
| `icon`             | `string`  | `null`         | Icon to display.                                             |
| `customIcon`       | `string`  | `null`         | Custom icon in HTML format.                                  |
| `confirmText`      | `string`  | `'OK'`         | Text for the confirm button.                                 |
| `enableConfirm`    | `boolean` | `true`        | Enables confirm button.                                      |
| `onConfirm`        | `function`| `function() {}`| Callback function when confirm is clicked.                   |
| `onCancel`         | `function`| `function() {}`| Callback function when cancel is clicked.                    |
| `enableCancel`     | `boolean` | `false`        | Enables cancel button.                                       |
| `cancelText`       | `string`  | `'Cancel'`     | Text for the cancel button.                                  |
| `enableCloseHandler` | `boolean` | `false`      | Enables a custom close handler when the dialog is closed.    |
| `onClose`          | `function`| `function() {}`| Callback function when the dialog is closed.                 |
| `clickToClose`     | `boolean` | `false`        | Allows clicking "close button" to close it.              |
| `OutsideClose`     | `boolean` | `false`        | Allows clicking outside the dialog to close it.              |
| `autoClose`        | `boolean` | `false`        | Automatically closes the dialog after the specified duration.|
| `duration`         | `number`  | `3000`         | Duration before auto-close (in milliseconds).                |
| `preogressBar`     | `boolean` | `false`        | Shows a progress bar for the duration.                       |
| `isDark`           | `boolean` | `false`        | Enables dark mode for the dialog.                            |
| `animation`        | `string`  | `'slide'`      | Animation style (`slide`, `fade`, `zoom`).                     |
| `input`            | `string`  | `null`         | Type of input field (`text`, `number`, `email`, etc.).                |
| `inputPlcaeholder` | `string`  | `''`           | Placeholder for the input field.                             |
| `inputMask`        | `string`  | `null`         | Mask for the input field.                                    |
| `size`             | `string`  | `null`         | Dialog size (`sm`, `md`, `lg`, `xl`, `2xl`, `3xl`, `4xl`).                        |

## License
This plugin is open-source and available under the MIT License.