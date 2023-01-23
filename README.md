# Lap
[12/5/22 2:57 PM] anilalexander195 (Guest)
https://github.com/peaceiris/actions-gh-pages

[12/5/22 2:58 PM] anilalexander195 (Guest)
https://github.com/simple-elf/allure-report-action

[12/5/22 2:58 PM] anilalexander195 (Guest)
https://github.com/AnilCa1905/Allure_Report_MakeMyTrip

[12/5/22 3:22 PM] anilalexander195 (Guest)
Headless 

[12/5/22 3:22 PM] anilalexander195 (Guest)
      'browserName': "chrome",      'acceptInsecureCerts': true,      'goog:chromeOptions' : {args:[  '--window-size=1920,1080',  '--incognito',  '--headless',],

[12/5/22 4:08 PM] anilalexander195 (Guest)

name: Node.js CI
on:
workflow_dispatch:
push:      branches: [ "master" ]jobs:   allure:    name: Generate Allure Report    runs-on: ubuntu-latest    steps:      - uses: actions/checkout@v2      - name: Get Allure history        uses: actions/checkout@v2        if: always()        continue-on-error: true        with:          ref: gh-pages          path: gh-pages      - name: Install Dependencies        run: npm install       - name: setup Latest Chrome Driver        run: npm run chromeDriverUpdate      - name: Executing the Test Scripts        run: npm run makeMyTrip        - name: Allure Report action from marketplace        uses: AnilCa1905/simple-elf-Repo@master        if: always()        #id: allure-report        with:          allure_results: test\.artifacts\allure-report          #gh_pages: gh-pages          #allure_report: test\.artifacts\allure-report          allure_history: allure-history          keep_reports: 20      - name: Deploy report to Github Pages        if: always()        uses: AnilCa1905/Peaceiris-gh_pages@v2        env:          PERSONAL_TOKEN: ${{ secrets.GITHUB_TOKEN }}          PUBLISH_BRANCH: gh-pages          PUBLISH_DIR: test/.artifacts/allure-report    

[12/9/22 5:35 PM] anilalexander195 (Guest)
    stages:        - test postman_tests :        stage: test         image:                name: postman/newman_alpine33                entrypoint: [""]         script:             - newman --version              - npm install -g newman-reporter-html              - newman run Ak_Tavels.postman_collection101.json --reporters cli,html,junit --reporter-html-export report.html --reporter-junit-export report.xml     artifacts:              when: always               paths:            - report.html                  reports :                 junit: report.xml

[12/19/22 5:06 PM] anilalexander195 (Guest)
document.addEventListener("mouseup", function(e) {
  let x = e.clientX;
  let y = e.clientY;
  console.log("Coordinates: (" + x + ", " + y + ")");
});

[1/17 3:45 PM] anilalexander195 (Guest)
npm install chromedriver@107 --save-dev

[9:58 AM] anilalexander195 (Guest)
 const str =  {                           "action" : "sendBasicAuth",                "arguments": {                    "timeout": 3000,                    "username": "admin",                    "password": "admin",                }                   };               const obj = JSON.parse(JSON.stringify(str));               await driver.executeScript(obj);

