## Security workshop

The goal of this workshop is to provide a minimal installer to install the Ethereum App on a Ledger device.

## Setup 

// TODO -- installer to upload

## Commands if you want to run it with the CLI

### 1. Clone the repository
```bash
git clone git@github.com:LedgerHQ/ledger-live.git
```

### 2. Install dependencies
```bash
pnpm i --ignore-scripts
```

### 3. Build the CLI
```bash
pnpm build:cli
```

### 4. Get device information (Optional)
```bash
pnpm run:cli deviceInfo
```

You should see something like this:

```json
{
  "version": "1.0.1",
  "mcuVersion": "6.3.0",
  "seVersion": "1.0.1",
  "mcuBlVersion": undefined,
  "majMin": "1.0.1",
  "providerName": null,
  "targetId": "********",
  "hasDevFirmware": false,
  "seTargetId": "********",
  "mcuTargetId": undefined,
  "isOSU": false,
  "isBootloader": false,
  "isRecoveryMode": false,
  "managerAllowed": false,
  "pinValidated": true,
  "onboarded": true,
  "bootloaderVersion": "5.3.0",
  "hardwareVersion": undefined,
  "languageId": 0
}
```

**Important**: Make sure that the device is unlocked (`pinValidated: true`)

### 5. Install Ethereum app
```bash
pnpm run:cli app --install ethereum
```

## Troubleshooting

### Version error
If you get a version error, you may need to update the firmware on the device.

```bash
pnpm run:cli firmwareUpdate
```

You'll have to accept the update on the device, twice:
1. First time it will ask you to confirm the update
2. After 30 seconds, it will ask you to confirm the enablement of the secure mode