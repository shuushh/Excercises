# Excercise
Create a test suite for OpenWeather API.

## Software/packages used:
* <a href="https://www.postman.com/downloads/" target="_blank">Postman</a>
* <a href="https://nodejs.org/en/" target="_blank">Node.js</a> & npm
* newman package `npm install -g newman`
* newman-reporter-htmlextra package `npm install -g newman-reporter-htmlextra`

### To run a test suite open your console and enter the command below
DO NOT forget to enter report output path or just delete export option and report will be saved to `newman/` default forlder. 

`newman run "https://api.getpostman.com/collections/11780178-0d37b47d-8d75-46a0-ba74-6b60ff1a5c6e?apikey=PMAK-5eef741f68aeb9004357ae80-241c40e1029f25d8b417efe2ddcc810668" \ --environment "https://api.getpostman.com/environments/11780178-b26a8c43-f6ee-423a-a02a-0ff825e07783?apikey=PMAK-5eef741f68aeb9004357ae80-241c40e1029f25d8b417efe2ddcc810668" -r htmlextra --reporter-htm-export "{ENTER YOUR DESIRED LOCATION}" --reporter-htmlextra-title "OpenWeather API Tests Report"`

Generated sample report preview can be accessed <a href="https://htmlpreview.github.io/?https://github.com/shuushh/Excercises/blob/master/OpenWeather%20API%20Sample%20Report.html" target="_blank">here</a>.
