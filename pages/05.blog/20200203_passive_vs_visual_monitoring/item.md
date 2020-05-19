---
title: Passive vs. Visual Monitoring
date: 09:00 02/03/2020

hero_classes: parallax text-light title-h1h2 overlay-dark-gradient hero-large
hero_image: alyvix_blog_article_passive_vs_visual_monitoring.png
show_sidebar: true

taxonomy:
    category: blog
    tag: [windows, virtual machine, rdp, rdc, it service, visual monitoring, real user monitoring]
---

Abstract.

===

# A Comparison Between Real User Monitoring and Visual Monitoring

Real User Monitoring (RUM) is a type of *passive* monitoring that tracks application availability and responsiveness by constantly observing a system using background services. A RUM system collects data exclusively from actual user sessions, which requires analyzing incoming internet traffic. This type of monitoring captures and analyzes each transaction individually as users interact with websites and applications.

Unlike RUM, Visual Monitoring doesn’t require any actual website visitors or application users to perform its tests. Instead it simulates human behavior by replaying the interaction paths (series of clicks, drags, etc.) end users take through that website or application. Obviously in order to probe your relevant interaction paths (or *test cases*), you have to identify those business-critical processes that you want to monitor.

Visual monitoring is a type of active monitoring, and since its interaction stream is artificially generated, the resulting traffic unlike with RUM is just a byproduct of testing. In other words, RUM infers results by searching through the entirety of user traffic and extracting only what it needs, while visual monitoring creates the specific traffic it needs and then measures just that traffic, so it doesn't need to store it long term.

Both methods collect data and measure application performance issues to ensure that potential problems don't reduce employee productivity and increase costs. But since RUM infers problems from inspecting real user traffic, by definition a problem has already occurred and the user has probably already noticed it.

In this case, visual monitoring tools are clearly more useful: because they have actively attempted to discover problems (by repeatedly running their test cases at regular intervals), they will be much more likely to find any problems before users do. It thus keeps many potential user complaints from ever arising because it can alert system administrators early, allowing them to solve issues before users can come across them.

That's not to say RUM is useless – for instance it's very helpful at understanding long-term trends. But if you stay awake at night worried that users will swamp the support department, you should definitely consider adding visual monitoring to your suite of tools. And both RUM and visual monitoring focus on the perspective of the user experience, where other more traditional monitoring techniques look at the performance and characteristics of individual services and hardware, apart from the user.


## Real User Monitoring - Advantages

* You don’t need to predefine test cases, because RUM captures every user transaction
* By analyzing the collected data, a service provider can find out the root cause of the problem


## Real User Monitoring - Disadvantages

* The storage requirements for the collected data are without doubt intensive. This often makes it very difficult to distinguish the relevant data from all of the noise
* It can be difficult to get useful information, because it requires looking at the traffic of actual people, which raises privacy and security concerns
* It can be quite difficult to identify persistent issues, or problems that slowly worsen over time


## Visual Monitoring - Advantages

* Issues can be found and fixed before they impact end users
* It can emulate complex business processes and user transactions from multiple geographic locations in order to measure performance
* You can monitor end user performance at any time, deciding according to your needs how often to check and from what location in the world
* Don't need to store very large network logs
* You can monitor third party applications and microservices regardless of whether or not they have an API, which is important for e-commerce websites that often rely on third-party add-ons and payment modules


## Visual Monitoring - Disadvantages

* Test cases can sometimes be too predictable, as they are built within a predefined environment may not match the full range of user behavior
* Test cases must be created by hand, and thus there is a limit on how many can be implemented, and you need to anticipate potential sources of problems


## In Conclusion

Visual monitoring, like other proactive monitoring strategies, can help you resolve problems before your users are even aware they are occurring. The overlap between its capabilities and drawbacks and those of RUM is quite complementary, so the best solution may be to combine real user monitoring together with visual monitoring.
