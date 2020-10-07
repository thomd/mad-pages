# lighthouse(1)

    lighthouse https://www.example.com

Options

    --view                                                 # open report in browser
    --chrome-flags="--headless"                            # run headless browser
    --output=json                                          # generate json report
    --output-path=./report.json
    --only-categories=performance
    --emulated-form-factor=desktop                         # emulate mobile/desktop
    --throttling-method=provided                           # throttle provided/simulated conditions
    --extra-headers "{\"Authorization\":\"Basic abc=\"}"
    --blockedUrlPatterns=*.googletagmanager.com'

## Configuration

Create config file `lh.js`:

    module.exports = {
       extends: 'lighthouse:default',
       settings: {
          chromeFlags: ['--headless']
          onlyCategories: ['performance'],
          throttlingMethod: 'simulate',
          emulatedFormFactor: 'mobile',
       }
    }

and run

    lighthouse --view --config-path=./lh.js https://www.example.com

## Chrome Flags

    --headless
    --disable-gpu
    --disable-software-rasterizer
    --disable-dev-shm-usage
    --no-sandbox
    --show-paint-rects
    --window-size=1920,1080
    --remote-debugging-port=9222
    --hide-scrollbars
    --screenshot
    --print-to-pdf
    --dump-dom
