# TransportForLondon
This framework is built using .Net 6 and C#. The test scripts have been written using Specflow to support BDD. 

Before running the tests, 
- update the Url in appSettings.json file 
- update the BrowserType (HeadLessChrome or Chrome) in appSettings.json file 

TransportForLondon.sln has a class library 'PageObjects' and 'Tests' project where the feature files are present. 
The tests focuses on the functionality of 'Plan My Journey' widget in the URL /tfl.gov.uk/'
Browsers are initialised and closed in the 'BrowserHooks' class which would execute at the beginning and end of each scenario in the feature file. 
Since new browser is opened for each test, cookies are being accepted at BeforeScenario block in 'BrowserHooks' class.

Test Scenarios: 
1.Verify that a valid journey can be planned using the widget
This test takes in two parameters for From and To locations and validates the journey in Plan My Journey Widget.
Scenario Outline with Examples is used to add more valid journeys to the test.

2.Verify that the widget is unable to provide results when one or more invalid locations are used

This test is to verify the error messages when invalid locations are entered Plan My Journey Widget.
Scenario Outline with Examples is used to add more invalid locations based on the input field criteria like number of characters, alphanumeric and special characters.

3. Verify that the widget is unable to plan a journey if no locations are entered into the widget
This test is to verify the error messages when no locations are entered in From and To locations in Plan My Journey Widget.

4. Verify change time link on the journey planner displays 'Arriving' option and plan a journey based on arrival time
This test verifies the arriving time on the results page based on the Arriving/Departing option selected in the scenario. 
It accepts 'Arriving' and 'Departing' as time options and if the value is incorrect or if no value is passed, it defaults to 'Arriving' and selects the Arriving link. 

5. Verify that a journey on the Journey results page can be amended by using the Edit Journey button
This test verifies that on editing an existing journey using 'Edit Journey' button, the locations are updated and the results are displayed. 

6. Verify that the Recents tab on the widget displays a list of recently planned journeys
