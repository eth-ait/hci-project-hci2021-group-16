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

![Good growth](https://github.com/eth-ait/hci-project-hci2021-group-16/blob/2021/img/web1.PNG?raw=true)
![Bad growth](https://github.com/eth-ait/hci-project-hci2021-group-16/blob/2021/img/web2.PNG?raw=true)

This forest would grow and change as your habits with CO2 emissions change as well. When you stop compensating your CO2 emission levels, the forest starts to die and you will see that the trees start to lose their leaves. When you start compensating you will recieve a popup where your forest is now blooming and swinging happily. This will continue until you unlock various rewards such as a virtual background or stickers to thank you for your compensation levels. Likewise, it is possible to have in-store rewards so that you actually end up saving more money shopping by compensating to reduce the CO2 emission levels.

![Reward page](https://github.com/eth-ait/hci-project-hci2021-group-16/blob/2021/img/web3.PNG?raw=true)

### Feedback Carbon Busters
Group 07: The character choosing buttons were not clear, she didn’t know what they did(but that is mainly because the mid-fi prototype is not accurate enough).
She said the numbers on the ghosts were confusing. 
The fact that the counter starts at 0 is good
Maybe adding next to the money on the slider the amount of CO2.
She liked the layout in the page.
She liked the fact that the characters are humans. 
She liked the comparison of CO2 to ghosts
The small animation is a nice plus. 
She would have liked to have a learn more button on the first page.

Group 10: She liked it because it is playful and interactive
The numbers on the ghosts were confusing 
She would have liked a learn more button on the first page
It’s not intuitive what you have to do at first, maybe change the UI?
She said it’s special and she hadn’t seen this approach anywhere else. 

Group 13: They hadn’t watched ghostbusters before so they weren’t very familiar with the topic. Therefore, he wasn’t as interested in the design. Also the different colors didn’t make sense to him but that had to take some explaining to clear up. In addition, he thought that the design was simple but liked the idea of having a slider to determine what amount of CO2 you can compensate for. He wanted more information on why there were ghosts as well.

TA: His concern was that of the A/B testing, the main core of this idea is visual, yet the course is about interaction, so we have to think about what will we test and how much interaction the user will have with the plugin. 

### Feedback Browser Extension Forest
Group 07: She really liked the simplicity of the design and how it was visually. She felt that having your personal forest you would get attached to it, so it would be a nice incentive to keep it alive. 
The user said that maybe more info about the widget (a learn more button) would be useful. She also liked the fact that it’s a pop up, so you can access it anytime.

Group 10: Didn’t understand what happened when the trees completely died and wasn’t sure if you could revive it. Also really liked the simplicity of the design. Wanted more control over what you could do with the plans and trees in the forest. Also had some suggestions on what should be in the rewards store such as discounts on purchases and collectable points/trophies. She said that this was easier to use and implement than carbon busters.

Group 13: Really liked the simplicity of the design and the idea that the forest was always there. He didn’t like how one of the rewards was a sticker because wouldn’t that create more CO2. Which is true and made me realize there needs to be mainly virtual rewards only. They also liked how there was a breakdown of where the CO2 came from.

TA: Thought it was cool to have a simple design but felt like there needed to be more interactivity. Thought both designs were nice but felt that there needed to be much more buttons and things to do and shouldn’t just be something that you watch the entire time. Liked the simplicity of the tree and forest design and how it tracks overall consumption and has a life-long history.

### Feedback Conclusion
In light of the feedback we received from Groups 7, 10 and 13 and from the TA, we decided to discuss possible paths of development for our two Mid-Fidelity Prototypes, the Carbon Busters and Browser Extension Forest. 
 
The focal point for most of the positive feedbacks was the simplicity of design for our both prototypes, and the main negative feedback centered around the lack of interaction on both our prototypes. For that reason, we tried to come up with different ways to improve the level of interaction of our prototypes while keeping the interface simple. Upon further discussion, we decided that Carbon Busters would enable a path for development with a higher level of interactivity. One example that we came up with was adding drop down lists on the cloud of carbon dioxide, detailing the origin of the emissions with various charts for more interested users. Otherwise, the graph would not be visible, keeping the interface clean and simple.
 
Another reason for choosing Carbon Busters over the Browser Extension Forest is the nature of the two prototypes. We had planned for Carbon Busters to be a plugin that would be included in the final phase of a purchase on websites such as Galaxus and Amazon. As a result, it would be visible to more user, regardless of their existing environmental concern, which will hopefully inspire people who are not normally environmentally conscious to compensate for their actions. The Browser Extension Forest, being an extension that has to be installed manually by users, would probably pique the interest of people who are already environmentally conscious, which would potentially limit the userbase.

## Hi-fidelity Prototype Preparation
Based on the Feedback, we decided to pursue the Carbon Buster Idea for our HiFi Prototype and drop the forest browser extension. 

We want to keep the simplicity of the design as much as possible, as this was a main positive conclusion from the feedback and should therefore remain. On the other hand, we need to add an option to show more information about the CO2-causes. Also more Information should be displayed by default on the page, like total emission in kg and maybe a comparison to familiar emissions like car miles or flight distances. We are however still unsure on how to implement this while still keeping it as simple as possible. We’ll have to discuss this with the TA in the next exercise session.

As one of the testers wasn’t familiar with the Ghostbusters and thus couldn’t make sense of the  ghost figures we will try to replace these with more cloud like versions to represent emissions better. We also want to change the “Buster”-Figurine to a “tree man” to better represent the action of taking up CO2 but still keeping it playful with the CO2-Sucker in the hands. Also the color selection for the CO2-Buster was often misunderstood or confusing, so we’re probably gonna drop this option.

We plan on keeping the UI from the MidFi Prototype in its basic looks but will add additional functionality like clickable Ghosts/Clouds to display more info, as well as better functionality for the slider bar. We plan on adding a tank to the CO2-Sucker to act as a display for compensation projects or total compensated CO2.

All in all, the compensation task should also involve a bit more user interaction than in the MidFi, with the goal to get the user better informed about the roots of his CO2 emissions as possible and create engagement to compensate.

We want to keep the option open of adding virtual rewards for overcompensating, coming from the second MidFi Prototype. But we are still not sure, if this would lead to a better experience or just useless over complication of the process.

For the programming environment we settled on using Javascript with Vue, as it was advertised as the beginner friendliest tool. Some of us are still beginners in front end development and have no previous experience in javascript, so this makes sense.

We plan on evaluating three sets of A/B tests.
As a first variation, we would like to test two different input methods for the amount of CO2 to be compensated. One option is to offer a slidebar with continuous input. The other option is to use checkboxes, where the user can only choose discrete values.
Secondly, we would like to encourage the user to find more information about their CO2 compensation by clicking on the ghosts/clouds. In particular, we want to try one version with growing and shrinking ghosts and another version with a fake cursor or finger/water drop animation.
Finally, we want to test the influence of the slider’s starting position. Shall the default slider position be at “no contribution to compensation”, i.e. negative compensation, or at “CO2 neutral”, i.e. net compensation equals to zero? In the case of checkboxes, we would test a version with a pre-checked box at “no contribution to compensation” and one at “CO2 neutral”.

After consulting with the TAs,  we decided to slightly modify the structure of our A-B tests in such a way that it make more sense. We decided to compare different slider formats instead of sliders versus checkboxes. Our initial idea was having a continuous slider where the position of the knob directly represents the amount to be compensated. On the other side of the test, we compare this with a discrete slider, where the value to be compensated increases in steps depending on where the knob is situated on the slider. For our second A-B testing, we decided to compare this whole concept of Carbon Busters with sliders with the existing sysem where the user simply ticks a checkbox to compensate for the whole carbon emission linked to that purchase.

## Hi-fidelity Prototype

    TODO
    
## User study

    TODO
