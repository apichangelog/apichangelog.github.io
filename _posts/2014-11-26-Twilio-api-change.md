---
layout: post
title: How Twilio APIs change while having developers on the founding end-points
status: live
---

[Twilio](www.twilio.com "Twilio") is one of the leaders of the platform movement, being the a cloud communications company, founded in 2007 looking to disrupt the telecoms industry. They have been one of the most successful API first companies and are revered in the API world as trails blazers of how they put engineers first and at the centre of their business. By being the best to enable engineers to build product on top of their platform they have become the go to company in the cloud communications space globally.

![](/img/TwilioAPIChangelog.png)

We have are lucky enough to chat with [Rob Spectre](https://twitter.com/dn0t "Rob Spectre on Twitter") who has been involved with much of the API change at Twilio to share some of their experience and insight on how to better manage change of API change as your needs and requirements evolve.

So we asked Rob what are some of the bigger plans for late 2014 and early 2015 at Twilio?

> “We are preparing for a API upgrade and a big price drop. These prices drops will be across international and domestic pricing. This has been possible due to the economies of scale achieved recently by Twilio. As our developer network has grown significantly the unit price economics improved, so we are excited to pass this onto our custommers.“

We then began to dive deeper into how change has occurred at Twilio. The example Rob discussed was enabling MMS for USA long codes. There was a need to add a new parameter to the existing end-point.

So the process began with the product manager outlining the initial requirements and this document is shared across the relevant team of engineers. They begin to think through implications on different engineering build stories. When closer to launch they start implementing this in many languages consuming the APIs to ensure all frameworks are accounted for. This is then spread through the Twilio API evangelist community to ensure they are also validating this will be usable and useful for the community. 
Then if the evangelist group is cleared they will move onto a few major customers who are currently using the most similar endpoints. They validate with the customer their approach and enable testing initial. Twillio can dive further down on this to find those who are the best fit for new features by reviewing API logs, usage of endpoints and the use cases they are used for by API COnsumer. 

Aside: Like we discussed with [GoCardless](http://blog.apichangelog.com/2014/11/13/gocardless-apis.html  "GoCardless on API Changelog"), Twilio also has logs of all usage down to specific endpoints by individual consumers, so they can have in depth conversation with consumers when change is looking to be rolled out. 

MMS at Twilio was a neat design problem. The MMS protocol allows different media in the same message. Twilio wanted to show all media options and the spec allows for overloading of http spec. Each item would then be presented as a media URL. The problem was this broke in the Ruby on Rails and PHP frameworks. So their conclusion was they had to be more pragmatic on the solution they were going to provide. Thus they had to go for a more simple solution without overloading to ensure they could ensure this works in a clear and functional way for all developers. 

###To guarantee a service

Being able to guarantee service is a key part of the Twilio API.

Rob outlined when a company like Twilio exposes APIs / SDKs to the public in production, they are making a solemn promise to the developers that they are there to serve that API for the long term and change will occur in an intelligent and methodical fashion. Twilio have been experts in this process. According to Rob there are still some developers who are still using founding end points of their API. Probably a claim few companies can make.

So long term service is ingrained in the Twilio API strategy.

So back to adding MMS functionality to the Twilio API. So in this a case they decided to add a new end-point to their API which would be across message types i.e. SMS and MMS. As this would now have an enganced functionality across both, they decided to deprecate the existing SMS end-point. The SMS deprecation path was defined, which was to be one through to two years, depending on response from customers.

Keeping this type of consistency is the ongoing theme from our chat. From best practice point of view (other than Twilio), Rob saw Stripe as a leader in the field. 

> “They are exemplary at maintaining consistency across interfaces.“

Rob went to outline however In general in the API industry there is a tendency of covering mistakes from the past, by quick change and inconsistency, however working with those mistakes to not let down your API consumers must be thought of at all stages including when change is to occur. 

###Scope = customer impact not techincal difficulty

When scoping change, the key metric Twilio look at is the number of customers that are impacted not the scale of the technical change initially. This is why they have invested so much effort the v3 release and well as very granular tracking infrastructure across their API.

As discussed before, Twilio aims to have world class customer service organization for developers. Not many companies can say that and actually achieve it, their approach to managing their API does reflect that. 

If you want to chat to Rob and his team directly the quickest path is help@twilio.com, [twitter.com/Twilio](http://www.twitter.com/twilio "Twilio on Twitter") and don’t forget to follow them on [API Changelog](https://www.apichangelog.com/api/twilio "Twilio On API Changelog"). 



