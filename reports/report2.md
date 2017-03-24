Most Terrorism is Local
================

In this report, I explored the Global Terrorism Database (GTD). The database contains a collection of entries with information about terror attacks since 1970. Data from the year 1993 is incomplete, and so is not included in the dataset. I started my exploration by looking at the trends in attacks over time. It is pretty clear that there are a few notable trends. First, the total number of terrorist attacks and the average number of people killed in an attack have increased throughout the world. This is shown in Figure 1 and Figure 2. Looking at Figure 1, you can see that the residuals are very large over the last 4 points on the graph. These correspond to the years 2011-2015, which shows the impact the rise of the Islamic State of Iraq and the Levant (ISIL) has had on the data. Both of the slopes of the fitted lines are statistically significant and positive with p-values less than 0.01, but the slope of the deadliness of an attack is small. However, this is with the number of attacks increasing also, so the tiny increase in deadliness has lead to a larger number of individuals dying from terrorism each year.  

![figure1][chart1]

![figure2][chart2]

The regional hotspots of terrorism have also shifted over time. It has only been over the last two decades that the Middle East and South Asian regions have seen the greatest number of terrorist attacks. This is shown in Figure 3. However, while Figure 3 does nicely show how history has changed, it does not give any real insights that could not be found in a textbook. The plot of attacks by specific terror groups over time has a similar result, but due to the number of terror groups that have existed is more difficult to visualize cleanly. Part of this difficulty is that nearly 46 percent of terror attacks are done by unknown groups, which also adds some difficulty in trying to answer questions about how groups operate. The failure to identify the perpetrating group means that it is impossible to tell if the attack involved international logistics or not. 54 percent of attacks lack the domestic vs internationally planned classification, but unless 86 percent of the unkown are international, the majority of terrorist attacks are planned domestically. 

![figure3][chart3]

After exploring the database, I asked what factors make a country a target for a terrorist group. Specifically, I focused on 3 groups that get a lot of print in the United States: ISIL, Al-Qaeda, and the Taliban. Firstly, the database does not contain any country data such as population, GDP, diversity, etc., so my first step was to find additional datasets on country statistics. I started with economic data, using the Penn World Table 9.0 (http://www.rug.nl/ggdc/productivity/pwt/). However, the country name field and country code columns in the two datasets did not match up, and so I had to add a column containing information that could be merged on; plus, the GTD contains countries that no longer exist, but that did not effect the terrorist groups I chose. 

Results
-----------
![figure][chart4]

It turns out that the prevalence international terrorism is so minimal that no real conclusions can be drawn for a groups and in general. ISIL has a total of 7 terror attacks marked as international logistics, and they are all in the neighboring states of Turkey and Lebanon. The actual terrorist group with the most international terrorist attacks is Al-Shabaab, the group based in Somalia, and all of its international attacks are on nearby or neighboring nations as well. Therefore, it seems that the juiciest targets for terrorist are their own backyard and their neighbors. 

On a side note, at what point does a terrorist group become a state, and a national party become a terrorist group? This dataset has the problem that it is very susceptable to people's answer to that question, which can have a large effect when looking at a small subset of the data. 

[chart1]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown-5
[chart2]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown-7
[chart3]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown-8
[chart4]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown-6
