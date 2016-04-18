### Problem
DonorsChoose.org is a United States–based 501(c)(3) nonprofit organization that allows individuals to donate directly to public school 
classroom projects. Using the data provided by DonorsChoose.org, I would like to predict the following outcomes of a project - <br/>
1) If a project would be fully funded or not? If so, when would it be fully funded(duration)<br/>
2) Identify projects that are very successfull compared to others<br/>
3) Predicting Donor rentention<br/>
4) Which set of donors could be targeted for any given project ? <br/>

Also, I would like to answer the following questions using this data -<br/> 
1) What factors would contribute towards or negate the chances of a project being fully funded ?<br/>
2) What factors would contribute in a project being highly successfull, far surpasssing other projects, being funded very quickly ?<br/>
3) How important is the teacher written requests/essays for a project? And what factors contribute the most?<br/>
4) What would be the ideal way to target a donor? (Eg: By Post, By Email(and what time?), By a giving page etc)<br/>
5) What factors would contribute towards a donor return for another donation?

### Client 
The client here would be the non-profit organization - Donorschoose.org. It would help the client in several ways -<br/> 
1) To know the possible funding outcome of a project, so that the client is well prepared in advance. The Client could use this 
information to estimate and prepare for the material purchase from vendors. The client could use this information to change the priority in listing the project on the website <br/>
2) The Client could target donors for project funding based on the system's predictions and also the means of making funding requests
such as email, by post, by promotions etc <br/>
3) Getting to know the factors of a project success or failure would help the Client make improvements or suggest improvements to 
the teacher who requests the project <br/>
Eg: Location of project, Subject, Funding amount, Poverty level, Materials requested etc<br/>
4) Predicting donors that are likely to return could lead to higher efficiency and significant savings<br/>

### Dataset 
Link to data - http://data.donorschoose.org/open-data/overview/<br/>
**1) Projects** - All classroom projects that have been posted to the site, including lots of school info such as its NCES ID 
(government-issued), lat/long, and city/state/zip.<br/>
**IDs** - Project Id,Teacher Account Id, School Id<br/>
**School Location**<br/>
**School Types** - 6 types - Charter,Magnet,School Year Round,School Nlns,School Kipp,School charter Ready Promise<br/>
**Project Categories** - Primary/Secondary focus subject, Resource type, Poverty level, Grade level<br/>
**Project Pricing and Impact** - Total price of project, Number of students a project reaches<br/>
**Project Donations** - Total donation amount, Number of Donors<br/>
**Project Status** - Funding Status-Completed/Expired/Live, Date Created/completed/expired<br/>

**2) Donations** - All donations, including donor city, state, and partial-zip (when available)<br/>
**IDs** - Donation Id,Donor Account Id, Project Id<br/>
**Donor Info** - Donor location, Is teacher account ?<br/>
**Donation Amount and Type** - Type includes - via_giving_page: True if the donation was made through a Giving Page. for_honoree: Donation included an honoree.<br/>
**Payment Type** - different types of payment includes - Account credit, Gift cards, Credit card, Check<br/>

**3) Project resources** - All materials/resources requested for the classroom projects, including vendor name<br/>
**4) Project written requests / essays** - Full text of the teacher-written requests accompanying all classroom projects<br/>
