### Problem
DonorsChoose.org is a United States–based 501(c)(3) nonprofit organization that allows individuals to donate directly to public school 
classroom projects. Using the data provided by DonorsChoose.org, I would like to predict the following outcomes of a project - <br/>
* If a project would be fully funded or not? If so, when would it be fully funded(duration)<br/>
* Identify projects that are very successfull compared to others<br/>
* Predicting Donor rentention<br/>
* Which set of donors could be targeted for any given project ? <br/>

Also, I would like to answer the following questions using this data -<br/> 
* What factors would contribute towards or negate the chances of a project being fully funded ?<br/>
* What factors would contribute in a project being highly successfull, far surpasssing other projects, being funded very quickly ?<br/>
* How important is the teacher written requests/essays for a project? And what factors contribute the most?<br/>
* What would be the ideal way to target a donor? (Eg: By Post, By Email(and what time?), By a giving page etc)<br/>
* What factors would contribute towards a donor return for another donation?

### Client 
The client here would be the non-profit organization - Donorschoose.org. It would help the client in several ways -<br/> 
* To know the possible funding outcome of a project, so that the client is well prepared in advance. The Client could use this 
information to estimate and prepare for the material purchase from vendors. The client could use this information to change the priority in listing the project on the website <br/>
* The Client could target donors for project funding based on the system's predictions and also the means of making funding requests
such as email, by post, by promotions etc <br/>
* Getting to know the factors of a project success or failure would help the Client make improvements or suggest improvements to 
the teacher who requests the project <br/>
Eg: Location of project, Subject, Funding amount, Poverty level, Materials requested etc<br/>
* Predicting donors that are likely to return could lead to higher efficiency and significant savings<br/>

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
**5) Gift cards** - All website-purchased gift cards, including donor and recipient city, state, and partial-zip (when available)<br/>

####Limitations-
We do not have referral data i.e. For most of the cases, We do not know how a donor came to know about Donorchoose.org. However, we do have buyer data for donors who used a web-purchased gift card. Having referral data for all donors would be important for the company and help in ad campaign targeting. It could also help us in determining what donors are more likely to return for a donation or refer other donors.

####Data Cleaning/Wrangling-
Raw data was collected in a structured format in the form of csv files and loaded into pandas data frames. I had to merge projects data and donations data in a single data frame to get meaningful information such as - correlation between donor's state and project's state, plot between Primary focus subject and Average donation amount etc.<br/>
Other wrangling done - <br/>
* New attributes were created to help generate more interesting plots. For e.g.<br/>
  * Teachers who contribute to their own project were determined with the help of their account id matched with donor's account id for the same project.<br/>
  * Project completion percent(number of projects completed/Total number of projects) for different categories such as subject, poverty level of a school, number of students the project reached etc <br/>
* I had to remove whitespaces from the columns while reading data from the csv files <br/>
* Some rows had a mismatch of row values vs the columns they belong to. So they were handled.<br/>
* Additional uncessary columns created as a result of bad values in donor comments were removed.<br/>

***Data Cleaning to be done***-
A lot of other data cleaning is pending which involves getting meaning information from donations messages/comments from donors which could help in determining important facors contributing towards a donor's interest. A lot of data cleaning is required on the Project essay data which involves essays written by teachers while creating their projects. This could gives us important insights into the factors that contribute towards a project's success.

***Other Datasets that can be combined***-
* I have used average median household income data across different states from **U.S. Census Bureau’s 2014 American Community Survey (ACS)** to check its correlation with respective donation amounts across states.
* Other dataset that could be used is school's information from http://nces.ed.gov/ through a ncesId specified in the Projects dataset

### Data Exploration
1) How Subject category effects the performance of a project ?
![subject_projCompletion](https://raw.githubusercontent.com/maneeshj/data-science-intensive/master/Donor-Choose-Project/Images/subject_projCompletion.png)

![subject_projDuration](https://raw.githubusercontent.com/maneeshj/data-science-intensive/master/Donor-Choose-Project/Images/subject_projDuration.png)

* 'Other' subject under Applied learning scored the lowest
* 'Maths' under Math&Science scored below average. All other science scored high with Envrionmental Science being the highest
* 'Nutrition' scored the highest
* Parent involvement also scored very low
* Economics,Music and Sports scored high
* Financial literacy was funded the fastest and Other the slowest

2) How Students reach effects the duration of a project ?
![student_reach_proj_duration](https://raw.githubusercontent.com/maneeshj/data-science-intensive/master/Donor-Choose-Project/Images/student_reach_proj_duration.png)
The project duration is uniform untill a student reach of about 150-200. It varies a lot after that.

3) How Poverty level effects the performance of a project ?
![poverty_projects_performance](https://raw.githubusercontent.com/maneeshj/data-science-intensive/master/Donor-Choose-Project/Images/poverty_projects_performance.png)

**Hypothesis Test**
Hypothesis test on the significance of difference of sucesses of Highest poverty schoold vs remaining schools revealed a z-score of -50.4101979537. Hence there is a significant amount of difference between the sucesses.

**Poverty level vs Average Donation amount**
![poverty_donation_amount](https://raw.githubusercontent.com/maneeshj/data-science-intensive/master/Donor-Choose-Project/Images/poverty_donation_amount.png)

**4) How does school type affect performance of a project?**
Percentage of project successes if a school comes under a category is 72.52 and if a school doesn't come under any of the categories is 68.59. Hypothesis test reveals that, there is significant difference in the project sucess based on whether school has a assigned type or not.

**5) How do projects's resource types vary with donation amounts?**
![proj_resource](https://raw.githubusercontent.com/maneeshj/data-science-intensive/master/Donor-Choose-Project/Images/proj_resource.png)

Trips need the most donation amount folowed by Visitors


All the data exploration done so far are in the following links - <br/>
* [Projects Only Data Exploration](https://github.com/maneeshj/data-science-intensive/blob/master/Donor-Choose-Project/ProjectsOnly_DataExploration.ipynb)<br/>
* [Donations Only Data Exploration](https://github.com/maneeshj/data-science-intensive/blob/master/Donor-Choose-Project/Donations_Only_DataExploration.ipynb)<br/>
* [Projects merged with Donations Data Exploration](https://github.com/maneeshj/data-science-intensive/blob/master/Donor-Choose-Project/Projects_Donations_DataExploration.ipynb)

### Approach
**If a project would be fully funded or not? If so, when would it be fully funded(duration)<br/>
1) Identify projects that are very successfull compared to others<br/>
2) Predicting Donor rentention<br/>
3) Which set of donors could be targeted for any given project ? <br/>**
<br/>
To answer these questions, I would add all the features that I had described in my data exploration -
* Subject Category
* Number of students the project reaches
* Poverty level
* School type
* State of the project
* Project resource type eg: books,field trips
* Donor's state
* Donor category eg: teacher
* Donation type eg: via giving page
* Payment type eg: credit card
<br/>In addition to the above features, I would add other unexplored features and I would look at adding new dervied features. Also I would extract donor's comments (while making a donation) and this can be used as an important feature in determining why donor made a donation to a specific project. It could specially identify donors that would return for a donation.<br/>
All the above features can be added to a selected machine learning algorithm to make predictions.
