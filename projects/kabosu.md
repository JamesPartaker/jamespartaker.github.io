---
layout: projects
title: Kabosu
intro: Finding a place to rent in Canada is difficult
tags: Web Development / Ruby on Rails / Bootstrap / AWS

---

Canada has a rental property search problem. Right now the most popular way to find rental properties is through magazines found in brick-and-mortar stores. These magazines likely have huge distribution costs, are slow to update, difficult to search through and are altogether going the way of the dinosaur. Obviously, the internet has been invented since printing presses; which is fascinating. Especially with mobile technology coming into maturity there is a huge opportunity to create real value in this area. However, most current online solutions falter when it comes to usability and adoption, often because they were built in the Netscape era.

The goal when creating Kabosu was simple: Develop a better way for people to find rental properties in Canada.

### Designing The Homepage

In designing the homepage there were a few main concepts that I wanted to follow.

![Kabosu Screenshot](/images/kabosu_homepage_screen.png)
<div class="caption">Homepage screenshot</div>

**The user should quickly understand what the website does**. Often when browsing the internet you will come across websites that break the most basic usability rules by not explaining their product. The two headlines 'Rent the perfect place' and 'Apartments to rent in Winnipeg' are clear indications to the user of the websites purpose, above the fold. The background image also provides context.
    
**The next action to take should be clear**. The search bar framed in the middle of the page creates an obvious next step for the user. The magnifying glass icon tells the user that it is a search bar. The placeholder text, 'Enter a city, neighbourhood ...' gives direction. To reduce friction extra search fields were omitted from the homepage and added on the results page. 
    
**Instill a sense of value**. It is key that you Instill a sense of value both in yourself and the properties that you're listing. It is especially important when associating with other companies. I accomplished this by using a clean, well structured layout, and paying attention to details like alignment and spacing.


### The Technology

#### Back-end Framework
Ruby on rails is quite a popular framework to use these days and has a pretty established environment. I chose to use it because of its relatively quick development time and the fact that it has a large set of gems that can make development easier.

#### Maps  
Google's mapping solution has been king for years but more restrictive licensing & increased prices has lead to a push for an open solution. Open street maps has gained popularity as a data provider which has made it comparable in quality to Google's. I used MapBox as a tile provider which uses open street maps for its data source. Mapbox can be integrated using LeafeltJS, which is an open-source mapping library. Since you can use different tile providers with LeafletJS you are not stuck implementing a new API if you need to switch.

#### Layout
Tablets and devices with differing screen sizes have become more and more of the web market share. The need to accommodate these devices is crucial. Among a few other layout frameworks, twitter bootstrap is useful for creating responsive layouts that adjust to the device's screen size. A responsive layout was implemented across the website. Bootstrap also provides decent looking design elements that were used in the administration panel where utility, more than style, is key.

#### AWS
AWS was a natural choice for hosting. For a startup the advantage is in scaling quickly and easily to accommodate spikes in traffic. This advantage can trump the extra cost over using a fixed VPS hosting solution. AWS also provides other infrastructure services like a CDN, static hosting and DNS servers that compliment EC2. 

When it's relevant, many rails gems implement some sort of integration with AWS. In this case I used carrierwave for user image uploads which supports automatic uploading to S3. This makes it a matter of entering AWS credentials to implement something relatively sophisticated.

### Targeting SEO
    
A huge aspect of online marketing is search engine optimization. In this market there is an opportunity to capture search traffic for terms that specify the city or region ex) 'Apartments to rent in Waterloo'. Landing pages that target these search terms would be a part of a larger strategy.

![Kabosu Branding](/images/kabosu_branding.png)
<div class="caption">Kabosu branding</div>
