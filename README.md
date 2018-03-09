# Chatbots made easy workshop.

## After this you’ll be a Chatbot SUPER HERO!

* We will learn how to create an agent
* Then we will create a dialog with Dialogflow
* We will also test the dialog using Google Home Simulator
* Continue with building some custom entities

## What do we need?
* A fully charged laptop
* Internet connection
* A google user account (make sure you are logged with only one account in your browser)
* Some Node.js or JavaScript knowledge is helpful
* And that’s it, the ride begin in a few seconds

## Let’s create an agent
1. Let’s start by logging into Dialogflow. https://dialogflow.com/ 
2. Agents are best described as NLU modules.
3. Click on the “CREATE AGENT”

![](https://github.com/aliplanner/training/blob/master/images/let's%20create%20an%20agent.png)

4. Agent Name “sales_agent_assistant”, or what ever you like. We are creating an assistant to help us sell a used car. Choose API V2.

![](https://github.com/aliplanner/training/blob/master/images/sales_agent_assistant.png)

## What is an intent, let’s create one
5. An intent represents a mapping between what a user says and what action should be taken by your software.
6. Click on “CREATE INTENT”

![](https://github.com/aliplanner/training/blob/master/images/create_intent.png)

7. Name it “how to sell my car” and click on save. 
8. clicking on “Add Training Phrases”. 
9. Sample training phrases:
* I need some assistance to sell my car
* I am not sure how to sell my used car
* What is the easiest way to sell my car 
* Show me how to sell my car
* I am selling my car
* I want to sell my used car
* I need help with selling my car

![](https://github.com/aliplanner/training/blob/master/images/add_intent_phrases.png)

10. Now let’s add a response to this Intent. Click on “Add Response” link. For now we can add two sample responses for this step
* “Sure, I can help you with that. I will walk you through all the steps you need to take and things to know to sell your car to a private buyer in state of California. Are you selling online or in person?”
* “Absolutely, I will show how to sell your car to a private buyer in California, I will walk you through the steps and will provide you with all the information you need to know. Are you planning to sell it online or in person?”

11. Click on save and lets test the intent 
12. Click on “See how it works in Google Assistant”
13. Let’s test this on Google Home Assistant (AoG).
* Enter or say: “Talk to my test app”
* Let’s try one of the phrases we created

![](https://github.com/aliplanner/training/blob/master/images/simulator.png)

## Good Job
14. Congratulations
* We just created our first agent
* Added an intent with a few training phrases
* And tested it on Google Assistant! 

![](https://github.com/aliplanner/training/blob/master/images/good_job.png)

## How to extract information
15. What are entities and NER
16. Any important data you want to get from a user's request, will have a corresponding entity
17. Click on create entity
18. Call it “sell_method”

![](https://github.com/aliplanner/training/blob/master/images/create_entities.png)

19. Let’s create the following values and synonyms:
* Online : online, via internet, through the internet, through web, web, internet, digitally.
* In person: offline, old school, face 2 face, face to face.
20.  Click on “Allow automated expansion and Save.

![](https://github.com/aliplanner/training/blob/master/images/entity_variations.png)

## Let’s add a follow up intent
21. Click on create new intent and check on the follow up intent and select ”Custom”

![](https://github.com/aliplanner/training/blob/master/images/create_follow_up_intent.png)

22. Let’s call this intent: “online or in person”.
23. Let’s add the following phrases:

* In person
* Online
* Face 2 face
* I prefer to do it face to face
* I am old school
* I like to do it in the old school way
* Via web
* Through the internet
* It will be digitally
* I am selling in person

![](https://github.com/aliplanner/training/blob/master/images/phrases_with_entities.png)

## Let’s add a follow up intent

24. Let’s make sure that following values are visible in “Action and parameters” section:
25. Click on required and add the following prompts:
* Is it an online sell or in person?
* Are you selling in person or online?

![](https://github.com/aliplanner/training/blob/master/images/add_actions_2.png)

26. Now let’s add a few responses:
* Alright you are selling $sell_method, now it is best to have an estimate about the value of your car. Have you done your homework and have the value of the car at hand?
* Sure, $sell_method it is. Let's continue by determining the value of your car. Have you asked around how much your car is worth?
* $sell_method, to continue we would need to know how much your car is worth. Do you know about the value of your car?
27. Please save the intent and let’s test it on Google Assistant

## Let’s test the follow up intent
28. Let’s test this on Google Home Assistant (AoG).
* Enter or say: “Talk to my test app”
* Enter or say: “I am selling my car”
* Enter or say: “online” or “in person”

![](https://github.com/aliplanner/training/blob/master/images/simulator_intent_sell_methond.png)

## You are awesome
29. Congratulations
* We just created a follow up intent
* Created custom entities
* Extracted the custom entities
* And tested it on Google Assistant!

![](https://github.com/aliplanner/training/blob/master/images/you_are_awesome.png)

## Let’s create another entity
30. Name it “know_car_value”. Let’s add the following variations:
* Yes: yes, yep, sure, of course, I got it, I am covered, I have done my homework, I know the value, I know, I have done my research, yeah, I am good, aha.
* No: no, nope, nah, I am not sure, I am not sure how to do it, how can I do it, I need help with that, negative, I forgot to do it, I have to do it, show me how to do it, can you help with that, can you do it for me, please help me, find the price for me, you do it, can you do it on my behalf, can you do it

31. Make sure “Allow automated expansion” is checked. 

## Create another follow up intent
32. Now let’s create a follow up intent, click on follow up intent link, select custom, and let’s call this step “do you know the value”. 

![](https://github.com/aliplanner/training/blob/master/images/know_value_intent_follow_up.png)

33. Enter the following training examples. In case some values are not highlighted, please remove them, we will later go back to the entities section to add them there, and will return to renter them
* I would like to know if you can do it
* I have it covered
* It is covered
* Yes
* Yep
* Sure
* of course
* I got it
* I am covered
* I have done my homework
* I know the value
* I know
* I have done my research
* Yeah
* I am good
* Aha
* No
* Nope
* Nah
* I am not sure
* I am not sure how to do it
* how can I do it
* I need help with that
* Negative
* I forgot to do it
* I have to do it
* show me how to do it
* can you help with that
* can you do it for me
* please help me
* find the price for me
* you do it
* can you do it on my behalf
* can you do it
* No I have not done that
* I have not done it
* Have not done it
* Have not done that

![](https://github.com/aliplanner/training/blob/master/images/know_value_phrases.png)

34. Go to “Action and Parameters” click on “Required” and then click on the prompt column and type the following two prompts:
* Please let me know if you know how much your car is worth?
* Please let me repeat, do you know the price of your car?

![](https://github.com/aliplanner/training/blob/master/images/know_value_action.png)

35. Go to fulfillment and enable webhook call for this intent.
36. Save and time to create a fulfillment.

![](https://github.com/aliplanner/training/blob/master/images/know_value_fulfillment.png)

## Let’s create our first fulfillment
37. Click on fulfillment. To keep things simple for this workshop we are using the inline editor today. I highly recommend that you try the Webhooks later at home. 
38. Please enable the inline editor.

![](https://github.com/aliplanner/training/blob/master/images/fulfillment_disabled.png)

39. Please type the block below after line number 207:

```
'input.know_car_value': () => {
	let know_car_value = parameters.know_car_value;
	console.log("does the user know the price of the car = " + know_car_value);        
	if (know_car_value == "no") {            
		sendResponse("I would be glad to help you find the fair market value for you car. There are three resources that I can suggest, Kelley Blue Book, NADA Guides, and Autotrader.com. Let's try Kelley Blue Book for today. What is the make of you car?");            
	} else {
		sendResponse("One item checked, let's move on to advertisement. I can help you with advertising on Facebook, craigslist and on autotrader.com. So what do you think?");
	}    
},
```

40. Now let’s deploy

![](https://github.com/aliplanner/training/blob/master/images/fulfillment_know_value_code.png)

41. let’s test this in the simulator.
* Say or type “Talk to my test app”
* Say or enter “help me sell my used car”
* Say or enter “via the internet”
* Say or enter “No Can you help” OR Say or enter “I got it”

![](https://github.com/aliplanner/training/blob/master/images/simulator_know_value.png)

## You Rock!
42. Congratulations
* We just created a fulfillment
* Created an if else block
* And tested our Dialog on Google Assistant! 

![](https://github.com/aliplanner/training/blob/master/images/you_rock.png)

## Final stride, let’s create two more entities

43. Create a new entity and name it: advertisement_type
44. Click on the 3 vertical dots and select “Switch to raw mode” and paste the block below under the CSV tab:
```
"facebook","facebook","facebook ads","facebook advertisement","Instagram","Instagram and facebook","social media"
"craigslist","craigslist"
"autotrader","autotrader","autotrader.com","auto trader dot com"
"multiple","multiple","facebook and autotrader.com","all three","all of them","all","autotrader and social media"
```

45. Create the last entity for the evening and name it: car_make
46. Click on the 3 vertical dots and select “Switch to raw mode” and paste the block below under the CSV tab:
```
"car_make","Alfa Romeo","Aston Martin","Audi","Bentley","Benz","BMW","Bugatti","Cadillac","Chevrolet","Chrysler","Citroen","Corvette","DAF","Dacia","Daewoo","Daihatsu","Datsun","De Lorean","Dino","Dodge","Farboud","Ferrari","Fiat","Ford","Honda","Hummer","Hyundai","Jaguar","Jeep","KIA","Koenigsegg","Lada","Lamborghini","Lancia","Land Rover","Lexus","Ligier","Lincoln","Lotus","Martini","Maserati","Maybach","Mazda","McLaren","Mercedes","Mercedes Benz","Mini","Mitsubishi","Nissan","Noble","Opel","Peugeot","Pontiac","Porsche","Renault","Rolls Royce","Rover","Saab","Seat","Skoda","Smart","Spyker","Subaru","Suzuki","Toyota","Vauxhall","Volkswagen","Volvo"
```

## Final stride, let’s create two more intents
47. Create a new intent (not a follow up) and call it “Car make”
48. Add the following training phrases:
* Benz
* An old BMW
* I am driving a Jeep
* It is a Toyota

![](https://github.com/aliplanner/training/blob/master/images/car_make_phrases.png)

49. Make the parameter required and enter the following prompt messages:
* To proceed I would need to know the make of your car, what is it again please?
* To determine market value of your car I need to know its make. What is the make of your car if you would like to proceed? 

![](https://github.com/aliplanner/training/blob/master/images/car_make_prompts.png)

50. Finally, let’s add couple of responses: 
* $car_make.original is a great car, the fair market value for your car is around 000, time for placing ads online. I can help you with advertising on Facebook, craigslist and on autotrader.com. You can skip this step, or choose one or more items. How do you want to proceed?
* oh, $car_make.original is my favorite car, your car is worth  000, now it is time for advertisement. I can help you with advertising on Facebook, craigslist and on autotrader.com. So what do you think?

51. Please save and let’s create the last entity, we are almost there

52. let’s call it “advertisement type”. Please add the following training phrases for this intent:
* Craigslist is a no brainer
* I guess autotrader.com works better
* I like ads on instagram
* I prefer to place ads on facebook
* I would like to advertise on social media
* All three
* facebook

![](https://github.com/aliplanner/training/blob/master/images/ad_type_phrases.png)

53. Name of the action is “input.advertisement_type” and the parameter is not mandatory
54. Skip responses and activate “enable webhook call for this intent”.

![](https://github.com/aliplanner/training/blob/master/images/ad_type_actions.png)

55. Please click on fulfillment and add the following lines of code to your inline editor at line 219:

```
'input.advertisement_type': () => {
 	let ad_type = parameters.advertisement_type;
	let final_msg = "Please note that cold, hard cash is the easiest way to collect payment for a used car. The buyer might request a receipt for the cash.";        
	final_msg += " If you provide a bill of sale, this will serve as a receipt. When cars are sold for amounts over $2,000, a cashier's check is recommended.";        
	final_msg += " Thanks for using the system, it was great serving you today.";                	
	if (ad_type == "craigslist" || ad_type == "facebook" || ad_type == "autotrader") {
            let res_msg = "Perfect, I will create an ad for you and after your review and approval I will place it on " + ad_type + ".";
            res_msg += " " + final_msg;            
	    sendResponse(res_msg);        
	} else {
               sendResponse(final_msg);
	}
}, 
```

## Final stride, creating the last intent
56. Please click on create Intent, name it “how to collect payment” and add the following phrases:
* How to handle payment
* Is it ok to get a cashier’s check
* Should I accept a personal check
* Is it recommended to get a check
* Should I take cash
* How to collect money from the buyer

57. Please add the following two responses:
* Please note that cold, hard cash is the easiest way to collect payment for a used car. The buyer might request a receipt for the cash. If you provide a bill of sale, this will serve as a receipt. When cars are sold for amounts over ,000, a cashier's check is recommended.
* Cash is king. When cars are sold for amounts over ,000, a cashier's check is recommended. Accepting a personal check is not advised. If the buyer insists, stipulate you will not hand over the title until the check clears. Do not agree to a payment plan. This is an automatic red flag.

58. Please save. If you have noticed we are using some of the text we had entered earlier. 

## Final stride, let’s deploy and test
59. Please deploy and do the following in the simulator:
* Say or type “Talk to my test app”
* Say or type “Should I take cash”
* Say or enter “help me sell my used car”
* Say or enter “via the internet”
* Say or enter “no can you help”
* Say or enter “Ferrari”
* Say or enter ”social media” 

![](https://github.com/aliplanner/training/blob/master/images/simulator_know_value.png)

## We are done
60. You are unstoppable!
* We just created two more entities
* Added three new independent intents
* Created another fulfillment
* Deployed the code, and tested our first full fledged Chatbot

![](https://github.com/aliplanner/training/blob/master/images/chatbot_superhero.png)

