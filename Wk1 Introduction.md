
SUBMISSION QUESTION TO ANSWER
    Clearly define a problem or an idea of your choice. 
    Remember that data science problems always target an audience and are meant to help a group of stakeholders solve a problem, 
    so make sure that you explicitly describe your audience and why they would care about your problem.

    This submission will eventually become your Introduction/Business Problem section in your final report. 
    So I recommend that you push the report (having your Introduction/Business Problem section only for now) 
    to your Github repository and submit a link to it.


    KEY POINTs
        predict severity of accident
        road closed - accident, traffic
        injured are in critical condition for helicopter and road closure to be happening
        weather and road conditions are factors in getting into an accident and how severe it'll be
        ---> so that you'll drive more carefully
        ---> so you can adjust your route



Introduction and Problem Description (Business Understanding)

There is a world wide competition underway! All major cities want to attract new businesses and workers that can grow their city into a model of prosperity. Seattle is in this competition.
One of the ways Seattle can compete better is to improve its livability score, specifically the transportation section of its livibility score. With 49% of workers driving to work, any improvements in this section would have a positive impact and go a long ways to improving daily life in Seattle.  

Within the city of Seattle, transportation is a major factor when resident's rate their quality of life. The better the transportation the higher the quality of life. Within the category of transporation there is public and private but both may experience delays getting from A-to-B. A lot of factors contribute to delays, example: time of day, traffic volume, road conditions, weather conditions and traffic accidents. Currently, drivers are only aware of delays along thier route when they encounter them. The more severe the incident the longer the delay as emergency response is generally perportional to the incident. The more severe the more emergency vehicles and first responders required. The city would like to help drivers avoid delays by giving them the ability to understand the current traffic situation, thus allowing them to adjust their travel plan in advance. Access to such planning information is expected to improve a commute and thus improve daily life in Seattle.

As a key stakeholder, Seattle city, would like to be able to present a graphical depiction of traffic incidents on the city website. Given the vast majority of incidents only impact traffic for two hours, the graphic should limit its content to vehicle accidents reported within the previous two hours. This information will be accessible to everyone with the main user community expected to be the personal vehicle driver.

Also, based on key paramaters, there will be the ability to predict the severity of an accident. The assumption in this model is that a prediction of severity will be based on the initial information provided by a caller. The caller, at minimum, should provide weather, road condition, light condition, vehicle and pedesterian information.