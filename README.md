# Subway_Machine_Prolog
The Prolog Subway Sandwich Machine offers users different options of meals and display the menu based on user's choice. The machine is also capable of recording the order and displaying the receipt.  

## Introduction  
The machine offers the following options:  
* __meal__ options
* __bread__ options
* __meat__ options
* __vegetable__ options
* __sauce__ options
* __top-up__ options
* __sides__ options  
  
Moreover, the machine can intelligently display the options selectively person’s previous choices:  
1. If the person chose a _veggie meal_, meat options should not be offered.  
1. If a person chose a _healthy meal_, fatty sauces should not be offered.  
1. If a person chose a _vegan meal_, cheese top-up should not be offered.  
1. If a person chose a _value meal_, no top-up should be offered.  

Based on the requirements above, the working sequence is designed in the following way:  
<img src = "https://github.com/StephanieMussi/Subway_Machine_Prolog/blob/main/Figures/FlowChart.png" width = 1000 height = 150>  

The full menu is as followed:   
* meal   
  * standard, value, veggie, vegan, healthy   
* bread   
  * italian_wheat, hearty_italian, honey_oat, parmesan_oregano, multigrain, flatbread   
* meat  
  * chicken_breast, ham, bacon, meat_ball, roast_beef, steak, tuna  
* veggies  
  * cucumbers, bell_peppers, lettuce, onions, tomatoes, olives, corn, pickles  
* sauce  
  * fatty_sauce  
    * chipotle_southwest, ranch, bbq, mayonnaise, mustard  
  * non_fatty_sauce
    * chilli_sauce, tomato_sauce  
* top-up  
  * cheese_topup  
    * processed_cheddar, monterey_cheddar  
  * non_cheese_topup  
    * egg_mayo, guacamole]  
* sides  
  * chips, cookies, hash_browns, yogurt, drinks  


## Demo
After implementing the machine, the following test cases are used to demonstrate the fulfillment of all requirements.   

The first thing before the testing is to declare the list of user's choices as "dynamic". This allows __SWI-Prolog__ to modify the lists on the fly.  
``` prolog
Dynamicall(0):- dynamic(chosen_meal/1),
                dynamic(chosen_bread/1),
                dynamic(chosen_meat/1),
                dynamic(chosen_veggies/1),
                dynamic(chosen_sauce/1),
                dynamic(chosen_topup/1),
                dynamic(chosen_sides/1).
```  


### Test case 1: Standard Meal
The choices are listed as below:  
* Meal: Standard  
* Bread: Parmesan Oregano  
* Meat: Roast Beef  
* Veggies: Cucumbers, Pickles, Olives  
* Sauce: Ranch, BBQ  
* Top-up: Processed Cheddar  
* Sides: Cookies, Drinks  

The results are shown as below:  
<img src = "https://github.com/StephanieMussi/Subway_Machine_Prolog/blob/main/Figures/Standard1.png" width = 460 height = 105>
<img src = "https://github.com/StephanieMussi/Subway_Machine_Prolog/blob/main/Figures/Standard2.png" width = 759 height = 908>
<img src = "https://github.com/StephanieMussi/Subway_Machine_Prolog/blob/main/Figures/Standard3.png" width = 412 height = 185>  


### Test case 2: Value Meal
The choices are listed as below:  
* Meal: Value   
* Bread: Italian Wheat  
* Meat: Tuna  
* Veggies: Lettuce, Bell Peppers  
* Sauce: Chipotle Southwest  
* Sides: Yogurt  

The results are shown as below:  
<img src = "https://github.com/StephanieMussi/Subway_Machine_Prolog/blob/main/Figures/Value1.png" width = 794 height = 890>  
It can be seen that top-up never appears in the ordering steps.  


### Test case 3: Veggie Meal
The choices are listed as below:  
* Meal: Veggie  
* Bread: Multigrain  
* Veggies: Pickles, Lettuce  
* Sauce: Chilli Sauce, Mustard  
* Top-up: Egg Mayo  
* Sides: Drinks, Hash Browns  

The results are shown as below:  
<img src = "https://github.com/StephanieMussi/Subway_Machine_Prolog/blob/main/Figures/Veggie1.png" width = 796 height = 862>
<img src = "https://github.com/StephanieMussi/Subway_Machine_Prolog/blob/main/Figures/Veggie2.png" width = 356 height = 169>  

It is shown above that meat never appears for the user who chooses veggie meal.  


### Test case 4: Vegan Meal
The choices are listed as below:  
* Meal: Vegan  
* Bread: Flatbread  
* Veggies: Corn, Onions, Tomatoes, Lettuce  
* Sauce: Chilli Sauce  
* Top-up: Gaucamole  
* Sides: (none)  

The results are shown as below:  
<img src = "https://github.com/StephanieMussi/Subway_Machine_Prolog/blob/main/Figures/Vegan1.png" width = 796 height = 737>
<img src = "https://github.com/StephanieMussi/Subway_Machine_Prolog/blob/main/Figures/Vegan2.png" width = 796 height = 197>  

As it can be seen, the only non-cheese top-up is displayed, and meat never appears.  

### Test case 5: Healthy Meal
The choices are listed as below:  
* Meal: Healthy    
* Bread: Honey Oat  
* Meat: Chicken Breast  
* Veggies: Onions, Pickles, CUcumber  
* Sauce: Tomato Sauce  
* Top-up: Moneterey Cheddar
* Sides: Yogurt  

The results are shown as below:  
<img src = "https://github.com/StephanieMussi/Subway_Machine_Prolog/blob/main/Figures/Healthy1.png" width = 796 height = 549>
<img src = "https://github.com/StephanieMussi/Subway_Machine_Prolog/blob/main/Figures/Healthy2.png" width = 661 height = 522>  




