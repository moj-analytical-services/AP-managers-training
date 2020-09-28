# 6. Communicating analysis

While the platform can be used to communicate analysis in the 'traditional' way by compiling graphics and reports, it also offers novel and powerful ways to present data and analysis to customers directly via an intranet address (web-app). When combined with platform automation abilities, this can provide a highly efficient, timely, and professional service to customers.

## Static web apps

Static web apps are essentially internet-hosted reports. They benefit from immediate distribution and all the good parts of the platform (data availability, reproducibility, automation)

Previously developed static web apps include

[This one](example1)  
[This too](example2)

## Interactive web apps

An interactive web app is an internet hosted report that allows the user to interactively change the content which is displayed to them. This might include selecting which data series appear together on a graph or filtering data in a table. They are appropriate for content where the user is likely to want to explore the data freely, or to make a report with a large scope more concisely organised.

The ways in which a user might wish to interact with the report must be anticipated and facilitated by the developer, and consequently the development time for an interactive app is longer and requires careful design to be intuitive to the user. Interactive apps on the platform are mostly deployed with R-shiny software and will require an analyst with appropriate experience.

Previously developed interactive web apps include

[This one](example1)  
[This too](example2)

## Controlling access

For all web apps on the platform there are controls for whom is able to access it.

- **Whitelisted networks** only allow access from a specific set of locations. Current options include the DOM1 network, Quantum network, 102 Petty France wifi network, MoJ Digital wifi and VPN network, or anywhere with an internet connection.

- **Individual authentication** requires users to sign-in before they can see the web app. Users are also required to be on a permitted network as above. User authentication is performed with either an emailed hyperlink or one-time passcode.

## Other considerations

Deploying analysis through the platform using a web-app also makes it possible to collect and analyse usage metrics. This could mean understanding how popular a report is, which parts are used the most, and the interest levels of particular users.

Versioning of the source code means old versions of a report could be maintained in parallel with updated versions at no extra burden.

Please be mindful that technical support for the AP is only within office hours, and that service cannot be guarenteed 100% of the time. It is possible that an app may occasionally be unavailable for a day or two. The impact of such a scenario on users and critical business should be considered when determining if a web-app is the right service.