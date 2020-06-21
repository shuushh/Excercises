# Excercise
Create a test suite for OpenWeather API.

## Software/packages used:
* <a href="https://www.postman.com/downloads/" target="_blank">Postman</a> - used to write requests and some needed scripts
* <a href="https://nodejs.org/en/" target="_blank">Node.js</a> & npm - required to install additional packages for test running in CLI
* newman package `npm install -g newman`  - command line runner for Postman
* newman-reporter-htmlextra package `npm install -g newman-reporter-htmlextra`  - used to generate comprehensive and visually attractive test reports

### To run a test suite via console use the command below
API key can be provided upon request

`newman run "https://api.getpostman.com/collections/11780178-0d37b47d-8d75-46a0-ba74-6b60ff1a5c6e?apikey={ENTER API KEY HERE}" \ --environment "https://api.getpostman.com/environments/11780178-b26a8c43-f6ee-423a-a02a-0ff825e07783?apikey={ENTER API KEY HERE}"`

#### To generate an HTML report run this command
DO NOT forget to enter report output path or just delete export option and report will be saved to `newman/` default forlder. 

`newman run "https://api.getpostman.com/collections/11780178-0d37b47d-8d75-46a0-ba74-6b60ff1a5c6e?apikey={ENTER API KEY HERE}" \ --environment "https://api.getpostman.com/environments/11780178-b26a8c43-f6ee-423a-a02a-0ff825e07783?apikey={ENTER API KEY HERE}" -r htmlextra --reporter-html-export "{ENTER YOUR DESIRED LOCATION}"

Generated sample report preview can be accessed <a href="https://htmlpreview.github.io/?https://github.com/shuushh/Excercises/blob/master/OpenWeather%20API%20Sample%20Report.html" target="_blank">here</a>.

_Full report can be downloaded from the repository or generated via `newman` CLI_

### To run a test suite on your computer you will have to download collection `.json` file from this repository and import it to POSTMAN
1. Open Postman and look for `Import` button
2. Select downloaded .json file and hit `import`
3. Set global variable `url` to `api.openweathermap.org/data/2.5/weather`
4. Open `Runner`, select the collection and run it

## What is being tested
* Check if unauthorized access is possible
* Check if city name is valid and matches, and response status
* Check if coordinates are valid and response status
* Check if switching `latitude` and `longitude` coordinates gives no error
* Validate response JSON schema

As OpenWeatherMap API seems to be read-only, most tests are checking for status code 200 to be true. Few requests can be considered as fillers to provide a cohesive run and somewhat imitate data validation. One of which is getting city names from https://restcountries.eu/ API to dynamically set a list of cities/coordinates into a variable which can later be used to do multiple checks for OpenWeatherMap "By city"/"By geographic coordinates" calls. The list of city names AND coordinates can be changed/updated in `Set ENVIRONMENT variables` request by modifying the `if` statement (PLEASE, see https://restcountries.eu/ for further guidance). 
All data is stored as environment variables during initial request from restcountries.eu API and unset after the first iterration. This allows to run the same set of data multiple times or easily update it and run the suite again with different set of data.
If tests are to be run one by one, it is required to run these requests beforehand - `Check Authorization`,`Authorization Fix`,`Set ENVIRONMENT variables` - as they provide needed data for the tests. Setting _`appid`_ as a global variable with OpenWeatherMap API key should allow to run tests individually. However, setting variables will still be required.

As an additional test I've ran a JSON schema validation to a somewhat mocked schema (took some parts of OpenWeather response JSON) and expected it to be valid.
