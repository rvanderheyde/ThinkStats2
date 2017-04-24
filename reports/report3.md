All the News
=========

In this report, I explored the Pew Research Center's News Coverage Index dataset. It contains data on stories published by different news sources over the period from January to May 2012. The stories in the dataset number 20,447 of which 1,977 are from newspapers, 3242 from online, 5,186 from network television, 6,472 from cable news, and 3,570 from radio programs. Variables encoded included story date, ID, prominance, duration or word count, source, format, and topic. Duration or word count seem to me like good proxies for what the media cares about (and maybe what the public cares about), as a newspaper or cable news station will spend more ink or time respectively on a more important story to them than a less important one. From this we must ask, can we predict how a story will be covered in terms of duration and word count?

![figure1][chart1]

Figure 1 above shows the cummulative distribution function of the story word count for all printed news media in the dataset. This includes traditional print sources such as The New York Times and Washington Post as well as their online versions, and solely online news sites such as FoxNews.com and CNN.com. From this, the majority of printed articles are less than 2000 words with a few outliers. 

[Figure 2]

Figure 2 shows the CDF of the word count of non-broadcoast media as shown in Figure 1 plotted with an analytic distribution that matches the data fairly well. For this data, it appears that a Weibull distribution matches the shape well, but slightly underestimates the frequency of longer stories. Using this information, we can predict the most likely values for the parameters of the Weibull distribution, k and lambda based on different data, to see how the distribution is affected by the source, topic, geographic focus, and lead newsmaker. To do this, I extend the classes Suite and Joint from ThinkBayes to create the Article class, which has a modified likelihood method that returns the likelihood of the word count showing up under a Weibull distribution with hypothesized k and lambda.  

[Figure 3] 

Figure 3 shows a contour plot of the probability of a certain value of k and lambda after the updating the Article class with word counts from The New York Times. The distance between contours is small meaning that it is highly likely that the value of the parameters are contained in that spot on the chart. This is clearer in the pmfs of the two parameters shown in Figure 4 and 5 below.

[figure 4]
[figure 5]

Despite the narrowness in the distributions of the parameters for the Weibull distribution, it does not appear that this indicates any large differences between sources and topics. While there are some differences between the distributions, the overlap is too large to draw any predictive value from this approach.

[figure 6]
[figure 7]

This is shown in the figures above where the Education and U.S. Foreign Affairs topics, have large overlap in the output distributions, as well as The New York Times and USA Today sources. What this probably indicates is that something else drives a story's word count. This could be industry standards, which prevents stories from deviating in length from each other too much between different outlets and topics. This could also be due to an insufficient amount of data once broken down between sources and topics. Each source had only a couple hundred stories, which might not be sufficient to differentiat two sources or topics.

[figure 8]
[Section quantifiying difference between NYTimes and CNN.com]

Due to time constraints, I was unable to explore the broadcast news portion of the dataset. However, the analysis done above should work similarly for broadcast news, and maybe there will be more differences between sources and topics in that area.
