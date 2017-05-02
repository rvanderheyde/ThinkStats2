All the News in 2010 and 2012
=========

What does the media value? To answer that I explored the Pew Research Center's News Coverage Index dataset from 2010 and 2012. It contains data on stories published by different news sources over the period from January to December 2010 and January to May 2012 respectively. The stories in the 2012 dataset number 20,447 of which 1,977 are from newspapers, 3242 from online, 5,186 from network television, 6,472 from cable news, and 3,570 from radio programs, with an additional 50,000 stories from the 2010 dataset. Variables encoded included story date, ID, prominance, duration or word count, source, format, and topic. Duration or word count seem to be decent proxies for what the media cares about (and maybe what the public cares about), as a newspaper or cable news station will spend more ink or time respectively on a more important story to them than a less important one. 

![figure1][chart1]

Figure 1 above shows the cummulative distribution function of the story word count for all printed news media in the dataset. This includes traditional print sources such as The New York Times and Washington Post as well as their online versions, and solely online news sites such as FoxNews.com and CNN.com. From this, the majority of printed articles are less than 2000 words with a few outliers. 

![Figure 2][chart2]

Figure 2 shows the CDF of the word count of non-broadcoast media as shown in Figure 1 plotted with an analytic distribution that matches the data fairly well. For this data, it appears that a Weibull distribution matches the shape well, but slightly underestimates the frequency of longer stories. Using this information, we can predict the most likely values for the parameters of the Weibull distribution, k and lambda based on different data, to see how the distribution is affected by the source, topic, geographic focus, and lead newsmaker. To do this, I extend the classes Suite and Joint from ThinkBayes to create the Article class, which has a modified likelihood method that returns the likelihood of the word count showing up under a Weibull distribution with hypothesized k and lambda.  

![Figure 3][chart3]

Figure 3 shows a contour plot of the probability of a certain value of k and lambda after the updating the Article class with word counts from The New York Times. The distance between contours is small meaning that it is highly likely that the value of the parameters are contained in that spot on the chart. This is clearer in the pmfs of the two parameters shown in Figure 4 and 5 below.

![figure 4][chart4]
![figure 5][chart5]

Despite the narrowness in the distributions of the parameters for the Weibull distribution, it does not appear that this indicates any large differences between sources and topics. While there are some differences between the distributions, the overlap is too large to draw any conclusions.

![figure 6][chart6]
![figure 7][chart7]

This is shown in the figures 6 and 7 above where the Education and U.S. Foreign Affairs topics, have large overlap in the output distributions, as well as The New York Times and USA Today sources. What this probably indicates is that something else drives a story's word count. This could be industry standards, which prevents stories from deviating in length from each other too much between different outlets and topics. This could also be due to an insufficient amount of data once broken down between sources and topics. Each source had only a couple hundred stories, which might not be sufficient to differentiate two sources or topics. However, the standard deviation between the means of the word count for different sources and between different topics was twice as large; this was also seem in the duration of broadcast media.

![figure 8][chart8]

It is also true that there is a clear difference between print and online news media. As shown in figure 8 above, CNN.com has shorter stories than the print version of the New York Times does, with a difference in their mean story length of 672 words.  Unfortunately, the data set is lacking more variables that could explain the difference, but clearly the type of the media has a large effect as the mean word count of the print version of the Los Angeles Times and LATimes.com (4pm capture) differ by 779 words. However, longer stories online does not necessarily mean that vistors stay longer. According to Nielson's 2012 report on news websites, visitors to CNN.com stayed 35 minutes and 27 seconds on average, whereas visitors to the NYTimes.com (whose story word count average is also larger that CNN.com's by over 300 words) stayed for only 19 minutes and 16 seconds. However, this may have nothing to do with the word count of stories on these websites and everything to do with the presence of various media types such as videos and slideshows, which CNN.com might have more of (considering it has a cable news show also) or placed on their page better. 

So, from all of this it seems that on the whole sources vary more on word count (and duration) than topics due, that there is a difference between the detail in a story based on its media sector. Unfortunately, these were the only conclusions that could be drawn. I looked for different datasets containing information on the news media, such as consumers' beliefs or add revenue, but was not able to find anything significant. The closest I got to something interesting was Pew's State of the Media Report, which has a table containing circulation numbers for the top 25 newspapers. However, the set of newspapers that make up the top 25 did not have enough overlap with the newspapers included in the NCI dataset.

[Nielson Report](http://www.nielsen.com/us/en/insights/news/2012/may-2012-top-u-s-web-brands-and-news-websites.html)

[chart1]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown-10
[chart2]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown-11
[chart3]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown-12
[chart4]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown-13
[chart5]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown-14
[chart6]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown-15
[chart7]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown-16
[chart8]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown-17
