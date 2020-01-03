The main purpose of the project is to build a conversational bot (chatbot)to help users discover restaurants quickly and efficiently and to provide a good restaurant discovery experience. The project brief provided to you is as follows.

The bot takes the following inputs from the user:
City: Take the input from the customer as a text field. For example:
Bot: In which city are you looking for restaurants?
User: anywhere in Delhi

Assumption is that Foodie works only in Tier-1 and Tier-2 cities. we have used the current HRA classification of the cities from here. 
https://en.wikipedia.org/wiki/Classification_of_Indian_cities .The bot is be able to identify common synonyms of city names, such as Bangalore/Bengaluru, Mumbai/Bombay etc. 

The chatbot  provide results for tier-1 and tier-2 cities only, while for tier-3 cities, it  replies back with something like "We do not operate in that area yet". 

Cuisine Preference: The bot takes the cuisine preference from the customer. It should list out the following six cuisine categories (Chinese, Mexican, Italian, American, South Indian & North Indian) and the customer can select any one out of that. Following is an example for the same:

Bot: What kind of cuisine would you prefer?

Chinese
Mexican
Italian
American
South Indian
North Indian
User: I’ll prefer Italian!

Average budget for two people: Segment the price range (average budget for two people) into three price categories: lesser than 300, 300 to 700 and more than 700. The bot should ask the user to select one of the three price categories. For example:

Bot: What price range are you looking at?

Lesser than Rs. 300
Rs. 300 to 700
More than 700
User: in range of 300 to 700 

While showing the results to the user, the bot should display the top 5 restaurants in a sorted order (descending) of the average Zomato user rating (on a scale of 1-5, 5 being the highest). The format should be: {restaurant_name} in {restaurant_address} has been rated {rating}.

Finally, the bot  asks the user whether he/she wants the details of the top 10 restaurants on email. If the user replies 'yes', the bot should ask for user’s email id and then send it over email. Else, just reply with a 'goodbye' message. The mail should have the following details for each restaurant:

Restaurant Name
Restaurant locality address
Average budget for two people
Zomato user rating

In this project, we built a chatbot for 'Foodie' and then deploy it on Slack.
Components of the project are as follows

NLU training:  rasa-nlu-trainer to create more training examples for entities and intents.we used regex features and synonyms for extracting entities.

we Built actions for the bot. we have Read through the Zomato API documentation to extract the features such as the average price for two people and restaurant’s user rating. we built an ‘action’ for sending emails from Python.

Creating more stories: we Used train_online.py file to create more stories. we have given reference for sample conversational stories provided above.

Deployment (Optional): we have Deployed  the model on Slack.
