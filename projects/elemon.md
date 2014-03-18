---
layout: projects
title: Elemon
intro: Fun little iOS game built using cocos2d-x
tags: Game Development / Cocos2d-x / C++

---

Social games have been gaining popularity over the past few years. Unfortunately, some have been brazen in their attempts at extracting money from people by using manipulative tactics. They focused on building the game around these tactics, which was seen as a detriment to the quality of the gameplay. This lead a huge backlash against these 'pay-to-win' style games. 

As much as social games got a bad rap, I think that mobile apps are still a great platform to be able to build a great experience. They're still the new and cool thing that people love to talk about, and so I think there is an opportunity to create something that people really value.

![Elemon Logo](/images/elemon_logo.jpg)
<div class="caption">Elemon logo</div>

### Inspiration

There were three main sources of inspiration for Elemon.

#### Creativity of Zoo Tycoon &amp; Rollercoster Tycoon

People love to create things, Zoo Tycoon & Rollercoster Tycoon were amazing games that excelled in this way. Starting a new park was creating a new blank canvas where you could just imagine building the fastest, biggest rides or the most spectacular exhibits. It was important to give people enough freedom that they would have a sense of pride when they built their park. It was easy to get lost in building your park, seeing your creation coming to life, bit-by-bit. There was definitely some human instinct that this appealed to.

#### The Imagination of Pokemon

Pokemon has an appeal like no other, I mean who doesn't love cute, colourful, fun animals? Pokemon really captured the imagination with mythology, character and story. There was enough mystery behind the world to make it intriguing to follow and learn about. 

Rather than just plopping down boring, predictable animals, there is a sense of excitement every time you see a new Elemon that you haven't encountered before. Creating a world where there is an unknown element would be much more compelling for players to explore. As a game designer, this gives you an opportunity to add gameplay elements that may not make sense in a world that is true to our universe. What if there were 'Elemon' that could affect the weather, or could be combined to give special powers?

#### Social &amp; Community

Now I wouldn't call it a source of inspiration because of the bad track record, but the last cornerstone is social. Social aspects can give a sense of community, working together with your friends to progress through the game can be rewarding. Collecting in-game items that can be shared amongst your friends would be a fun way to collaborate. Even watching your friends build their park alongside yours would be motivating.

### The Technology

#### The Game Engine

[Cocos2d-x](http://www.cocos2d-x.org/) is a solid 2D game engine that is being used by some popular iOS games. It's based on the iOS engine cocos2d, but written in C++. With its ability to compile cross-platform to iOS, android and other mobile platforms it was a no-brainer. To add to that, it doesn't have any licensing costs; this was a huge benefit when compared to other game engines that can take a percentage of revenue or have a hefty upfront fee.


#### Building a pathfinding system

A-star pathfinding is quite prevalent in games today. In Elemon, there were characters that needed to find their way around the park. A-star was perfect in that I wanted to weight tiles so that characters would walk along realistic paths. The characters should prefer to walk on paths instead of grass, also to walk around impassable objects like buildings.



![Elemon In game screenshot](/images/elemon_in_game.jpg)
<div class="caption">(super alpha) In game screenshot where players could build buildings, exhibits and terrain</div>

![Elemon](/images/elemon_park_interface.jpg)
<div class="caption">Concept showing building, fence and terrain layout on a grid system</div>

![Elemon](/images/elemon_card_rock.jpg)
<div class="caption">Rock element trading card</div>

![Elemon](/images/elemon_card_water.jpg)
<div class="caption">Water element trading card</div>