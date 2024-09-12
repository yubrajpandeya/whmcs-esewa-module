# eSewa WHMCS Payment Gateway Module

This WHMCS module integrates the eSewa payment gateway, allowing users to make payments directly via eSewa for WHMCS invoices. The module handles payment requests, callbacks, and transaction logging.

---

## Features

- Seamless eSewa payment integration with WHMCS.
- Support for **Test Mode** and **Live Mode** environments.
- Automatic updating of invoice status upon successful payment.
- Transaction logging for easy debugging and tracking.

---

## Prerequisites

- WHMCS version 8.x or higher.
- Active eSewa Merchant Account:
  - **Merchant Code**
  - **Secret Key**

---

## Installation

1. **Download or Clone** the repository:
   ```bash
   git clone https://github.com/yubrajpandeya/whmcs-esewa-module.git
2. **Extract the Files** to your WHMCS installation directory:
   ```bash
   /whmcs/modules/gateways/
   ```
   The file structure should look like this:
   ```bash
   ├── modules
   │   ├── gateways
   │   │   └── esewa.php
   │   └── callback
   │       └── esewa.php
   ├── helpers.php
   ├── init.php
   ├── logo.png
   ├── whmcs.json
   ```

3. **Activate the Module**:
   - In the WHMCS Admin Dashboard, go to:
     - **Setup** > **Payments** > **Payment Gateways**
     - Select **All Payment Gateways** and activate **eSewa**.

4. **Configure the Module**:
   - **Merchant Code**: Enter your eSewa Merchant Code.
   - **Secret Key**: Enter your eSewa Secret Key.
   - **Test Mode**: Set to `true` for testing or `false` for live transactions.

---

## Configuration

In `init.php`, ensure you configure the necessary parameters:

```php
$params['MerchantCode'] = 'NP-ES-YOURCODE';
$params['SecretKey'] = 'YOURSECRETKEY';
$params['TestMode'] = true;  // Set false for live transactions
```

---

## Usage

- After successful configuration, customers will be able to select eSewa as a payment option during checkout.
- The module will process the payment and automatically update the WHMCS invoice status.

---

## Troubleshooting

### Common Error: `{"error_message":"Service unavailable.","code":0}`

This error may occur due to:
1. **Invalid API URL**: Ensure you're using the correct API endpoint (test or live).
2. **Invalid Credentials**: Double-check your Merchant Code and Secret Key.
3. **eSewa Server Downtime**: Check with eSewa if their servers are down.

### Enable Debugging

To assist with troubleshooting, enable transaction logging by adding the following code to `esewa.php`:

```php
logTransaction($gatewayModuleName, $paymentData, 'Payment Data Sent');
logTransaction($gatewayModuleName, $result, 'API Response Received');
```

---

## License

This module is open-sourced software licensed under the [MIT license](LICENSE).

---

## Contributors

- **Yubraj Pandeya** - Development
- **Suraj Datheputhe** - Initial Inspiration

For any support or questions, feel free to create an issue or reach out.
```

Make sure to copy the full markdown text again, and it should render properly when pasted into your **README.md** file. The formatting should appear as intended with proper sections and indentation.
