# Maestro Mobile Automation

Mobile UI test automation using [Maestro](https://maestro.mobile.dev/), covering a phone + OTP login flow for an Android app, written as composable YAML flows.

## Structure
```
flows/
  login.yaml           # top-level flow, orchestrates the steps below
  steps/login/          # small, reusable step flows (given/when/then style)
```

Each step is its own file so flows can share steps instead of repeating UI interactions - the same pattern used to build out further flows (onboarding, KYC, payments, etc.) on top of this one.

## Running locally
Requires Maestro CLI and an Android emulator/device/app installed.

```bash
maestro test flows/login.yaml -e TEST_PHONE=9000011224 -e OTP_DIGIT_0=1 -e OTP_DIGIT_1=1 -e OTP_DIGIT_2=1 -e OTP_DIGIT_3=1 -e OTP_DIGIT_4=1 -e OTP_DIGIT_5=1
```
