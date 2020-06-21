# Excercises
Pre-requisites for tests to run:
* Node.js (https://nodejs.org/en/) & npm
* newman package `npm install -g newman`
* newman-reporter-htmlextra package `npm install -g newman-reporter-htmlextra`

From console run this command to generate an html report at your specified location
`newman run "https://api.getpostman.com/collections/11780178-0d37b47d-8d75-46a0-ba74-6b60ff1a5c6e?apikey=PMAK-5eef741f68aeb9004357ae80-241c40e1029f25d8b417efe2ddcc810668" \
    --environment "https://api.getpostman.com/environments/11780178-b26a8c43-f6ee-423a-a02a-0ff825e07783?apikey=PMAK-5eef741f68aeb9004357ae80-241c40e1029f25d8b417efe2ddcc810668" -r htmlextra --reporter-htm-export "C:\Users\shuushh\Desktop" --reporter-htmlextra-title "OpenWeather API Tests Report" `
