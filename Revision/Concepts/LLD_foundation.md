# Foundational Pattern

1. Strategy Pattern
2. Factory Pattern
3. Singleton Pattern
4. Observer Pattern
5. Command Pattern
6. Decorator Pattern
7. Adapter Pattern
8. Facade Pattern


- Note :- The aim is simple like in our application there is two parts in our application one is static or stable code and other is unstable or not static so using these patterns we have to separate that dynamic code part from static code part to make our application maintanable, scalable and expandable.




# 1. Strategy Pattern

- This generally says that we have to use the composition over inheritance.
- Like I walk through a story okk so u understand what was actually that as described below
- मान लो की अपने को एक application design करनी है related to robot simulation, in that application we have some methods like robot can walk , talk and projection initially then later we try to add the the fly also like so we add it and we noticed after adding if we introduce like that then another fly robot came then we do more like that and broke the DRY Principal here.Later we realised that if we go with inhritence we face the hirachial inheritance problem that might a problem because in future if we add more then we have to do change lots of things so as we already know that in future if we want add some new feature then minimum code change so for that we used here composition so as per our eg we made the RobotClass and Talkable Interface, Walkable Interface and Flyable Interface and more like that and also write their concrete method as well.
- Uber Ride System, Notification System are some of the real world eg .
- अपने को ये समझ आया कि जब अपने को Different Alogrithm or strategy बनानी हो तो we use like that .
