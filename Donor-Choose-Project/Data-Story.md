
The idea of donorschoose.org is pretty simple. It lets public school teachers from across the country to request much-needed materials 
and experiences for their students and donors could donate to projects based on their interest.

The idea of this article is to answer questions such as - <br>
1) What kind of projects would be more successfull and based on what factors ?<br>
2) What kind of donors would be more generous ?<br>
3) What kind of donors would interest what kind of projects ?<br>

Here is how the projects performed in terms of the percentage of projects sucessfully funded under a subject category-

![subject_projCompletion](https://raw.githubusercontent.com/maneeshj/data-science-intensive/master/Donor-Choose-Project/Images/subject_projCompletion.png)

Nutrition, Environmental Science, Economics, Financial Literacy, Music and Team sports scored the highest, wheare as Other and Parent Involvement scored the least. This clearly shows that if a project is not assigned to any category, the chances of getting sufficient  funds would reduce. It could also mean that, donors consider subject as an important factor while deciding on what project to choose.  Donors also tend to prefer a project that has focus on a particular subject and not on projects that involves parent involvement. 

Now, let's look at how the projects performed in terms of the state they belong to-

![state_projCompletion](https://raw.githubusercontent.com/maneeshj/data-science-intensive/master/Donor-Choose-Project/Images/state_projCompletion.png)

According to **U.S. Census Bureau’s 2014 American Community Survey (ACS)**, the poorest and richest states based on the average median household income, are as follows-

Poor States | Rich States
------------ | -------------
Mississippi(MI) | Maryland(MD)
West Virginia(WV) | New Jersey(NJ)
Arkansas(AR) | Alaska(AK)
Alabama(AL) | Connecticut(CT)
Kentucky(KY) | Hawaii(HI)
Tennessee(TN) | Massachusetts(MA)
Louisiana(LA) | New Hampshire(NH)
New Mexico(NM) | Virginia(VA)
South Carolina(SC) | California(CA)

Looking at the data above, we can see a definite correlation between the average median household income of a state and the success rate of a project(the success rate here is the percentage of projects fully funded). This could mean that, the state of the school in which the project is based of has an impact on a donation. And there could be a correlation between the state of the donor and the state of the project. Let's look at this correlation below for a sample set of states - 

**Table - State wise Projects vs Donations**

States |  NY   |   DC   |  	CA   |   SC   |  	NV   |   IA
---- | ------ | ------ | ------ | ------ | ----- |  -----
NY | **57.3121** | 0.423177 | 6.1593 | 0.0900104 | 0.0861968 | 0.161488
DC | 11.7059 | **27.2631** | 4.60637 | 0.128401 | 0.0393744 | 0.275746
CA | 9.40677 | 0.34173 | **58.4186** | 0.0485834 | 0.106149 | 0.0574352
SC | 10.8145 | 0.222739 | 5.34664 | **42.3813** | 0.0739814 | 0.115496
NV | 9.52517 | 0.311637 | 26.9805 | 0.021724 | **36.9311** | 0.0664827
IA | 8.59265 | 1.21878 | 6.96014 | 0.0369313 | 0.071499 | **25.6568**

A row here is a state in which a project belongs and the columns are the states where the donations came from. For example, for a project that belongs to New York(NY) state, on an average 6.16% of the total donations come from California(CA) state. Looking at the diagonal line, it clearly shows that a donor is more likely to donate to a project that belongs to school in their own state.
Apart from that, another interesting finding is a donor is more likely to donate to a project that belongs to a neighbouring state.
For example, look at the states below - 

Top 5 donations for a project in **District of Columbia** - 

States | Percentage Share   
------ | --------
DC  |  27.263134
NY  |  11.705908
VA  |   9.365090
MD  |   7.012761
CA   |  4.606375

Top 5 donations for a project in **Iowa** - 

States | Percentage Share   
------ | --------
IA  |   25.656841
IL  |  25.329843
NY  |  8.592648
CA  |   6.960143
WI  |   3.600954

For a project in **DC**, a significant number of donors come from it's neighbouring states - **Virginia** and **Maryland**.
Similarily for a project in **Iowa**, a significant number of donors come from it's neighbouring states - **Illinois** and **Wisconsin**.
Another important observation here is that, most of the donors in general come from New York and California and they contribute a significant amount of share irrespective of which state the project belongs to.

Now let's look at the different types of donors we have - 
1) A teacher who donates to his/her own project
2) A teacher who donates to a project that belongs to another teacher
3) A non teacher (Majority of donors)

Let's look at their average donation amount-

![Donor_Avg_Donation](https://raw.githubusercontent.com/maneeshj/data-science-intensive/master/Donor-Choose-Project/Images/donor_avg_don_amt.png)

A person who is not a teacher is likely to be more generous than a teacher. And there are a lot of teachers who donate a significant amount to their own projects. And teachers contribute very less to projects that they don't own.
