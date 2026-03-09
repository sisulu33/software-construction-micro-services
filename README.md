# Microservices: Adoption & Architecture Trends
Microservices is  when you build an app as a bunch of small, independent services that each do one thing and talk to each other through APIs. 
The opposite of microservices is a monolith, which is one big application that handles everything together.


## Netflix

Netflix is the biggest example brought up when talking about microservices.In 2008, they had a major outage that took their service down for three days straight, all because of a single database corruption in their monolithic system. 

Over the next few years, they broke their entire system down into hundreds of smaller services. Each one handled something specific — like authentication, recommendations, billing, or video delivery. The big benefit was that teams could update or scale their part without messing with everything else.

What I thought was cool is that Netflix also built a bunch of tools to manage all of this, and they open-sourced them:

- **Eureka** – helps services find and talk to each other
- **Hystrix** – stops one broken service from crashing everything else
- **Zuul** – acts as a gateway that routes traffic to the right service
- **Chaos Monkey** – randomly shuts down services in production to make sure the system can handle failures

By the mid-2010s they were running over 700 microservices. Their setup became the go-to reference for a lot of other companies trying to do the same thing.


## Other Companies That Used Microservices

**Amazon**
Amazon was doing something like microservices before the term even existed. Jeff Bezos sent out what's now called the "API Mandate" in the early 2000s, telling every team they had to expose their functionality through APIs with no exceptions. This basically forced the whole company to think in terms of independent services. It also ended up being the foundation for AWS, since they could take all that internal infrastructure and sell it to other companies.

**Uber**
Uber started with a basic monolithic app, which made sense when they were just a small ride-sharing startup. But as they expanded into different countries and added new products like UberEats and freight, the monolith couldn't keep up. They switched to microservices so different teams could work independently. At one point they had over 2,000 services running. That said, it wasn't all smooth — they ran into issues with debugging across so many services and it became hard to onboard new engineers.

**Spotify**
Spotify is interesting because their architecture actually reflects how their teams are organized. They have small teams called "squads" that each own their own services. They also built a tool called **Backstage** to help engineers keep track of all their microservices — it's now open source and used by a lot of other companies too.

**Twitter**
Twitter's original app was built on Ruby on Rails, and it struggled badly during big traffic spikes. The "fail whale" error page became kind of a meme because it showed up so often. They moved to microservices and it made a big difference — they were able to handle huge events like elections or sports finals without going down.

**LinkedIn**
As LinkedIn grew, their monolith just couldn't scale anymore. They split things up into microservices and even built their own framework called **Rest.li** to standardize how all their services communicated. That framework is also open source now.


## Companies That Switched Back to a Monolith

Some well-known companies tried microservices and ended up going back to a monolith because the complexity wasn't worth it for them.

**Segment**
Segment is a data company that went all-in on microservices — they had 140+ services at one point. But things started breaking a lot, and debugging across that many services was a nightmare. Engineers were spending most of their time dealing with infrastructure problems instead of actually building things. In 2020 they wrote a public blog post about going back to a monolith and said things got a lot better afterward.

**Prime Video (Amazon)**
This one is kind of ironic given that Amazon basically invented the microservices culture. In 2023, the Prime Video team published a post about how they moved a video monitoring tool from microservices back to a single monolithic service. Their infrastructure costs dropped by 90% and the system got simpler and faster. They admitted that microservices had added a lot of overhead that wasn't actually necessary for what they were building.

**Basecamp**
Basecamp's co-founder DHH (he also created Ruby on Rails) has been pretty vocal about not needing microservices. Their products — Basecamp and Hey — are both built as what he calls a "majestic monolith." His argument is that most companies aren't Netflix-scale, and microservices bring a level of complexity that small and mid-sized teams really don't need.

**Stack Overflow**
Stack Overflow gets millions of visits a day and still runs mostly on a monolithic architecture with a small number of servers. Their engineers have used this as a point to push back against the idea that you automatically need microservices once you reach a certain scale. Sometimes good engineering and the right hardware is enough.


## My Takeaway

After going through all of this, I think the main lesson is that microservices aren't a one-size-fits-all solution. They make a lot of sense for huge companies with large engineering teams where different groups need to work independently. But for smaller teams, the overhead , managing all those services, debugging across them, keeping them all running, can slow you down more than it helps.

The trend I'm seeing now is that a lot of people suggest starting with a monolith and only breaking things into services when you actually have a reason to. That seems way more practical than just adopting microservices because it's what the big tech companies do.
