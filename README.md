## Security workshop

The goal of this workshop is to provide a minimal installer to install the Ethereum App on a Ledger device.

## Setup 



## Commands if you want to run it with the CLI

git clone git@github.com:LedgerHQ/ledger-live.git

pnpm i --ignore-scripts

pnpm build:cli

**Optional** pnpm run:cli deviceInfo 

You should see something like this:

{
  version: '1.0.1',
  mcuVersion: '6.3.0',
  seVersion: '1.0.1',
  mcuBlVersion: undefined,
  majMin: '1.0.1',
  providerName: null,
  targetId: ********,
  hasDevFirmware: false,
  seTargetId: ********,
  mcuTargetId: undefined,
  isOSU: false,
  isBootloader: false,
  isRecoveryMode: false,
  managerAllowed: false,
  pinValidated: true,
  onboarded: true,
  bootloaderVersion: '5.3.0',
  hardwareVersion: undefined,
  languageId: 0
}

Make sure that the device is unlocked (pinValidated: true)

pnpm run:cli app --install ethereum

Troubleshooting:

If you get a version error, you may need to update the firmware on the device.

pnpm run:cli firmwareUpdate

You'll have to accept the update on the device, twice (first time it will ask you to confirm the update, after 30 seconds, it will ask you to confirm the enablement of the secure mode).