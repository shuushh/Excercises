# Excercise
Create a test suite for OpenWeather API.

## Software/packages used:
* <a href="https://www.postman.com/downloads/" target="_blank">Postman</a>
* <a href="https://nodejs.org/en/" target="_blank">Node.js</a> & npm
* newman package `npm install -g newman`
* newman-reporter-htmlextra package `npm install -g newman-reporter-htmlextra`

### To run a test suite via console use the command below
DO NOT forget to enter report output path or just delete export option and report will be saved to `newman/` default forlder. 

`newman run "https://api.getpostman.com/collections/11780178-0d37b47d-8d75-46a0-ba74-6b60ff1a5c6e?apikey={ENTER API KEY HERE}" \ --environment "https://api.getpostman.com/environments/11780178-b26a8c43-f6ee-423a-a02a-0ff825e07783?apikey={ENTER API KEY HERE}" -r htmlextra --reporter-htm-export "{ENTER YOUR DESIRED LOCATION}" --reporter-htmlextra-title "OpenWeather API Tests Report"`

Generated sample report preview can be accessed <a href="https://htmlpreview.github.io/?https://github.com/shuushh/Excercises/blob/master/OpenWeather%20API%20Sample%20Report.html" target="_blank">here</a>.

### To run a test suite on your computer you will have to download collection `.json` file and import it to POSTMAN
1. Open Postman and look for `Import` button
2. Select downloaded .json file and hit `import`
3. Set global variable `url` to `api.openweathermap.org/data/2.5/weather`
4. Open `Runner`, select the collection and run it
