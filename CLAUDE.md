# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is the E2E testing suite for the web application using Playwright. 
It tests the complete user flows across multiple browsers and devices.

## Common Development Commands

### Test Execution
```bash
npm test                    # Run all tests
npm run test:headed         # Run tests with browser UI visible
npm run test:ui             # Run tests with Playwright UI mode
npm run test:debug          # Run tests in debug mode
npm run test:chrome         # Run tests only in Chrome
npm run test:firefox        # Run tests only in Firefox
npm run test:safari         # Run tests only in Safari
npm run test:mobile         # Run tests on mobile devices
npm run report              # Show test report
```

### Setup
```bash
npm install                 # Install dependencies
```

## Test Architecture

### Helper Functions
- **Cross-browser Testing** - Automated testing on Chrome, Firefox, Safari, and mobile devices

### Configuration
- **Failure Handling**: Screenshots and videos captured on test failures
- **CI Mode**: Stricter retries (2x) and single worker for stability when `CI=true`

## Important Technical Details

### Test Isolation
Each test starts with a fresh browser context and authenticated session to prevent test interference.

## Development Guidance

- Do not guess the test code! Open a webpage in Playwright MCP, analyze DOM, and write code only with real element locators
- Save each test scenario in a docstring. When updating a test, read the docstring first and make sure all steps are followed
- Run the test in Chrome afterward to make sure it passes, use headless mode
- Tests must always throw an exception in case of CAPTCHA because they can only work from the internal network or through VPN
- Fix the test until it passes, but ensure it still follows the steps in the docstring. Clarify if something is missing.
- Mobile-only tests must go into @tests/mobile and have a resolution of 430 × 932 pixels

