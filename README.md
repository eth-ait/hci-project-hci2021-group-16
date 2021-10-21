<p align="left" width="100%">
  <img height="56" src="img/logo-ait.png"> &nbsp; &nbsp;
  <img height="56" src="img/eth-sip-3l.png">     
</p>

# CO2 Compensation Visualization, Group 16
#### Mert Çökmez, Vikram Thanigaivelan, Raffael Kunz, George Selim, Yi-Tau Ly, (Leon Thomm)

## Project description

Our goal is to visualize and motivate CO2-compensation for users. Greenhouse gas effect has been a rising topic the last decade and remains important. Examples for activities that result in CO2 emission include but are not restricted to commuting, machine learning, streaming, shopping, etc. By visualizing the user's contribution to CO2-compensation, we wish to help them understand and grasp their impact and possibilities they have.

## Ideation

Summarizing our desktop research, there are a lot of online services that calculate the user's CO2 emission and/or enable the user to compensate for their carbon footprint through the service. Often, CO2 compensation is offered by planting trees or investing into climate sustainable projects on the behalf of the user. An example for real-time CO2 emission visualization is given on QUARTZ. It shows how many trees’ CO2 neutralizing capabilities the user has „used up“ since he or she has opened the Google webpage. On the other hand, the visualization of CO2 compensation is frequently shown as charts, certificates or checkmarks at the check-out process (e.g. Zalando or Flixbus). The current state of CO2 compensation visualization with numbers, charts and certificates does not satisfy us, because it is still hard for the user to grasp their impact through emission and compensation.
<br>Key points of our project are to visualize pollution and compensation. For example, an 8-bit tree or forest as a web-extention could represent the user’s current net CO2 emission or it could simply just flourish as you contribute to CO2 compensation projects and wither as you forget or have not contributed to such projects for a longer time. An easier way of visualizing CO2 compensation could be rendering a graph with the user’s CO2 emission and compensations over time or use a scale with an emission and a compensation side.
<br>Moreover, through our visualizations, we hope to motivate the user to compensate for the CO2 emissions they cause. This could be given in the form of social recognition through social media sharing posts or NFT plant tokens that you can collect and lose. More motivation could be triggered through rankings, either single or team based.  Also, we think that it is important to show or visualize the concrete results of the CO2 compensated.
    
## Evaluation

    TODO

## Low-fidelity Prototype

A: Forest Browser Extension

Web-extension forest grows as CO2 is compensated and shrinks/dies if the user emits too much CO2 or does not contribute to CO2 emission compensation. If the user does not compensate for CO2 emission for a month, a push notification will be sent.
We tried to keep the prototype as simple as possible whilst keeping key features. The web-extension shall be a calm guard of the user‘s CO2 compensations, keep him/her happy as long as the forest is taken care of, and alert the user when CO2 emissions are too high in relation to the compensations. We opted to use simplistic 8-bit caricatures and visualized them as a 2D-prototype.

B: CO2-Buster

This tool should be used by webshops or online booking websites to offer an interactive way of CO2-compensation, instead of the usual check mark we see on most websites today.
The CO2-Buster let’s you choose your desired amount of CO2 to compensate by a slider, ranging from 0% to over 100% of your emissions caused by your purchase. This offers you the option to help other buyers, who can not afford the compensation or didn’t bother to.
The design is focussed on a positive and encouraging user experience, animating the Emissions as a cloud and then sucking up the part of the cloud you compensated for in a satisfying animation and finally congratulating you, for your effort against climate change, but never judging you for choosing less than 100%.
The costs will then just be added on top of your bill, based on percentage chosen and thus the respective amount of CO2 to compensate, simple and easy.
The focus of this prototype is really on simplicity of use and positive user experience. All one has to do is slide a slider to the desired position, representing the amount to compensate.

C: Compensation Credits

The idea is here is a universal reward system, where all the user’s CO2 compensation is exchanged to tokens. Users have to make an account, where they will store their tokens. 
Our service offers many ways to redeem those tokens, as we have a store and many partnerships that offer our users discounts on products, the possibility to do more CO2 compensation(use the tokens to plant more trees) as well as a social media sharing possibility.  Paper prototyping made us reflect on the amount of info we want to add when offering a green buying choice, it also made us reflect how to present the options in terms of colors and extra steps that the user has to make before checking out. 

    
## Mid-fidelity Prototype
A : Carbon Busters

So the idea is like a parody of the famous cartoon GhostBusters, called Carbon Busters. 
On online shopping websites, right before checking out, you have a page with your order info, on that page we are adding a small game. 
The first thing you can do is choose your character (the 4 small circles), then move the slider(which is originally at the lowest value, 0). 
The slider determines how much money you want to pay for CO2 compensation, with a line determining the point where you are carbon neutral. We had the choice of letting the slider either control the amount of money payed or the amount of CO2 compensated, we preferred it showed the amount of money as it is more important to most users. As you can see, the slider allows users to become Carbon Positive.
The Carbon is visualized by the ghosts, we have a ghost for each source of carbon (Transport, production, etc)
To visualize how much of their emissions the users are compensating, we chose to keep it abstract. Most websites try their best to give users the easiest and more comfortable experience, if we start making users feel guilty about their purchases, our idea will not be adopted by the websites. 
So on each Ghost, you have a number, which represents how much(percentage) of that field of emission you have compensated. For example if the slider is on 10% compensation, the ghosts will show -90 on them, if the slider is on 150%, they will show +50. 
Another aspect is that the ghosts’ size grows with the slider growing, we also thought that a way to incite overcompensation would be to make the ghosts “like a puzzle”, meaning that only at 150% compensation they sit tucked together nicely in a visually satisfying way. 

After making those 2 simple choices, the user goes to the checkout page,  this page presents the confirmation of the order, and an animation of your character sucking in the ghosts play. 
Under this animation the website tells you how much CO2 you compensated, and presents a comparison with something concrete(liters of fuel, kms in a car, trees planted, etc.)
We chose to add this comparaison here, as it only shows a concrete example of how much the user compensated and not how much they emitted with their purchase. Which results in a better user experience, as they would feel better about themselves. Also for the more curious, they can click on the learn more button to find out how exactly the website compensates and what projects are implemented.

WALKTHROUGH VIDEO
https://drive.google.com/file/d/1M78UubB3j6UKLAwfGtzXocIIokS6COxE/view?usp=sharing

B: Forest Web Extension

Our motivation for this idea was to create something simple and omnipresent in your browser so that you are always aware of CO2 emission levels when purchasing new products. This idea we decided on was to create a virtual forest that would be present in the browser and could reprsent the user's total CO2 consumption and emission in a playful way. 

Firstly, the store shopping page would display the CO2 emission levels and have a choice of wheter you want to compensate or not. This will be a simple choice and you can also choose what percentage you would like to compensate. When this happens, the web extension will pop up your forest giving you a reminder of the current state of your forest and to remind you to compensate if you can as well as the impact if you don't.  

![Good growth](https://github.com/eth-ait/hci-project-hci2021-group-16/tree/2021/img/web1.png?raw=true)
![Bad growth](https://github.com/eth-ait/hci-project-hci2021-group-16/tree/2021/img/web2.png?raw=true)

This forest would grow and change as your habits with CO2 emissions change as well. When you stop compensating your CO2 emission levels, the forest starts to die and you will see that the trees start to lose their leaves. When you start compensating you will recieve a popup where your forest is now blooming and swinging happily. This will continue until you unlock various rewards such as a virtual background or stickers to thank you for your compensation levels. Likewise, it is possible to have in-store rewards so that you actually end up saving more money shopping by compensating to reduce the CO2 emission levels.

![Reward page](https://github.com/eth-ait/hci-project-hci2021-group-16/tree/2021/img/web3.png?raw=true)


## Hi-fidelity Prototype

    TODO
    
## User study

    TODO
