# AWS Device Farm

**AWS Device Farm** is an application testing service that lets you improve the quality of your web and mobile apps by testing them across an extensive range of real desktop browsers and real mobile devices, without having to provision and manage any testing infrastructure.

## Key Features
- **Real Devices**: Test on real, physical Android and iOS devices hosted in AWS data centers.
- **Desktop Browsers**: Test web applications on desktop browsers (Chrome, Firefox, etc.).
- **Automated Testing**: Run automated tests using frameworks like Appium, Calabash, Espresso, XCTest, and more.
- **Remote Access**: Interact with devices in real-time via a web browser for manual testing.
- **CI/CD Integration**: Integrate with Jenkins, AWS CodePipeline, and other CI/CD tools.

## Testing Types
| Type | Description |
| :--- | :--- |
| **Built-in Fuzz Test** | Randomly sends user interface events to devices and reports results. |
| **Custom Tests** | Upload your own test scripts (Appium, XCTest, etc.). |
| **Remote Access** | Swipe, gesture, and interact with a device in real-time from your browser. |

## Use Cases
- **Regression Testing**: Automatically test new builds on multiple devices before release.
- **Compatibility Testing**: Ensure your app works across different OS versions and screen sizes.
- **Performance Profiling**: Collect metrics like CPU, memory, and network usage during tests.

## Exam Tips
- **Real Devices**: If a question asks about testing on **real mobile devices** or browsers, the answer is Device Farm.
- Differentiate from **AWS Amplify** (building/hosting apps) — Device Farm is specifically for **testing**.
