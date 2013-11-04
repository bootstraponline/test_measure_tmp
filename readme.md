#### flaky [![Gem Version](https://badge.fury.io/rb/flaky.png)](http://rubygems.org/gems/flaky) [![Dependency Status](https://gemnasium.com/appium/flaky.png)](https://gemnasium.com/appium/flaky)

Run Appium iOS tests to measure flakiness.

- `gem install flaky`
- `flake 3 ios[nop]` - Run the iOS test named nop 3 times.
- `flake 3 ios` - Run all the iOS tests up to 3 times.
If a test passes then it moves onto the next test.
If a test fails 3 times then it moves onto the next test.

Results are stored in `/tmp/flaky`

Must set `ENV['APPIUM_HOME']` to point to the appium folder containing `server.js`.

This only works with:

- [Ruby / appium_lib iOS](https://github.com/appium/ruby_lib_ios)
- iOS iPhone Simulator 6.1

#### Security dialogs

Instruments prompts for security authorization when testing on iOS.
Set the following environment variables in `~/.bash_profile`.
If you don't know your username, type `whoami` in the Terminal and use that value.

```
export FLAKY_USER="username"
export FLAKY_PASSWORD="password"
```

Ensure that Terminal has been granted permission to control the computer. This is set in Security & Privacy -> Accessibility.

![](doc/accessibility_terminal.jpg)

--

#### For each test:

- iOS Simulator is closed
- All `iPhone Simulator/6.1/Applications/*` are removed
- Appium server is restarted
- [spec](https://github.com/bootstraponline/spec) test logs are saved and colored
- [Appium](https://github.com/appium/appium) logs are saved and colored
- iOS Simulator logs are saved `/var/log/system.log`
