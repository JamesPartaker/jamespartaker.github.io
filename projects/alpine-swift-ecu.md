---
layout: projects
title: Alpine Swift Jet Engine ECU
intro: Building a super fast jet engine
tags: Embedded Development / Desktop Development / C / Java / Arduino
github: https://github.com/JamesPartaker/AlpineSwiftECU
---

My brother is a mechanical engineer who loves to use his degree to build crazy contraptions. We always came up with ideas to build things when we were younger, now we have the knowledge, why not use it? His latest project is to design and build a model jet engine. What? - A jet engine? Greeeaaat idea.

Well, these jet engines need controllers to run them - and my brother is the furthest thing from a programmer. He knew just the person that could help him. Initially I was a little skeptical, but after watching some youtube videos I couldn't say no.

[What is a model jet engine? (youtube)](http://www.youtube.com/watch?v=d5OiUAqEOmk)

[Watch a jet engine propelled plane go very fast (youtube)](http://www.youtube.com/watch?v=dTHWBSluUjU)

![Jet Engine Analysis](/images/as_analysis.jpg)
<div class="caption">Analysis of airflow around the combustion chamber - Modelled in ANSYS</div>

### The Engine

The base engine design is a turbojet engine. This is a relatively simple design compared to other jet engine designs like turbofans. Each design has unique characteristics that make it useful for different applications. Turbojets aren't as fuel efficient at lower speeds when compared to turbofans but can achieve higher speeds (ie. faster planes).

#### Setting Goals &amp; Innovating

Replicating something that's been done before isn't our idea of fun, we wanted to build some novel element to our engine. While we aren't going to redesign the entire concept of a jet engine, there were aspects that we wanted to improve. On model jet engines there is progress to be made in areas like reliability, power, efficiency, and ease-of-use. By taking a few hints from full-sized jet engines we can take some modern technology and retrofit it into a smaller scale.

Most of the current model jet engines use fuel vaporizer tubes that allow the fuel to be heated to a vapour before setting it into the combustion chambers. Unfortunately, vaporizer tubes have a limited life because of the extreme heat that they are subjected to. They practically melt away. Also, starting the engine is more difficult with this design because the engine is cold. A better approach to this problem is to use a fuel nozzle that atomizes the fuel mechanically.  This is the method that we are using.

The base engine is slated to produce about 76lb of thrust based on models. This is adequate for most applications of these engines, but if you can go more, why not? An afterburner adds another 'stage' on to the end of the base engine where you can add more fuel -- for more power. It essentially increases the maximum power at the cost of fuel efficiency. However, since this stage can be turned on and off, there is little cost when you're not using it.  

### The Engine Controller

The ECU (Engine Control Unit) has the responsibility of managing the engine to ensure proper operation. It can control the engine through its outputs to the fuel pump, ignition and start up motor. Decisions are based on data taken from its sensors: thermocouples and a hall effect sensor, measuring turbine speed. By listening to external commands the ECU can be told to perform operations like starting up, shutting down or setting the throttle.

#### Managing Fuel Flow

One decision that the ECU needs to make is how much fuel to add to the combustion chamber during acceleration. This decision has implications in the performance of the engine, but must be limited by the compressor's surge line. You cannot simply add a large amount of fuel into the combustion chambers quickly. Surge is a complicated phenomenon by which the airflow reverses direction rapidly. It causes violent vibrations that can damage the engine. By measuring the engine's speed and pressure, the fuel flow is carefully managed by the ECU.

#### And GO!

There is a specific procedure that the ECU follows in order to get the engine from a stopped position into a state where a user can throttle the engine. Once the ECU receives a control message to start up it follows instructions similar to these:
- Turn on the electric start-up motor
- Measure turbine speed until the turbine reaches 5,000RPM
- Start fuel flow
- Start the ignitor
- Check the temperature sensor for an increase in temperature (indicating ignition)
- Stop the ignitor
- Stop start up motor
- Increase fuel flow until the turbine reaches 40,000RPM
- Enter the running state

Once these steps are complete the user has control and can throttle the engine as needed.

#### Making Sure Things Don't Go Wrong

As the ECU is running it constantly performs critical tasks that prevent the engine from reaching a dangerous state. This arises from the fact that the mechanical components of the engine are rated for certain limits. For example, the turbine can only handle temperatures of 800°C and speeds of 115,000 RPM, over which the engine can see a drastically reduced lifespan or fail completely (OK, maybe spectacularly). If any of these conditions are exceeded the ECU must detect it, take over control and recover the engine to a safe state.

#### What's Going On Inside?

Since we are designing a custom engine there is some extra functionality that we want to build into our system. A terminal that communicates with the ECU during run-time is critical. The idea is that we will be able to control the engine, monitor performance and set variables for tuning the engine. The ECU sending back log messages lets us graph, analyze and record the conditions inside the engine. This lets us tweak parameters that affect engine performance using data gathered in previous runs. 

### The Technology

#### ECU

The ECU is currently being written on the arduino platform, which is essentially a development environment built on top of an Atmel micro-controller. The arduino is a good prototyping platform but may not be suitable for running something as critical as an ECU, at least without some modification. Often the arduino libraries aren't written in an acceptable way for a 'hard real-time' system. This will be investigated further.

#### Terminal

The terminal is a Java app. Initially, I chose Java because it's cross platform and I have experience writing Java. Unfortunately, when it came to a real-time graphing library there were few options. JFreeChart fulfilled the needs visually, but couldn't render quickly enough. I may need to move to another platform, possibly C\# with mono, or C++ with Qt.

![Alpine Swift ECU Terminal](/images/as_terminal_gui.png)
<div class="caption">Concept of terminal GUI layout</div>

#### Testing
Any errors in the ECU code could be disastrous for the engine, and so a thorough testing strategy is necessary. Unit testing, as well as system testing will be performed to ensure proper operation. I am looking at emulators/simulators and other tools that can help in the testing and debugging process. 


![Jet Engine Analysis](/images/as_parts.jpg)
<div class="caption">Jet engine parts - Compressor, Nozzle Guide Vanes and Turbine</div>
