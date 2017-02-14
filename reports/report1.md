Are Diseases of the Heart Periodic?
======================================

There are many diseases that are known to be periodic. Influenza and Pnuemonia, for example, see an increase in incidence during the winter months, which is why this season is known as "Cold and Flu season." This increase in incidence also leads to an increase in deaths due to Influenza and Pnuemonia, which can be seen in the figures below. 

![image1][chart1]

![image2][chart2]

But is heart disease periodic? To answer that, I examined the [CDC Wonder](https://wonder.cdc.gov/ucd-icd10.html) database on the underlying cause of death for the state of California organized by month. It turns out there are 23 groupings of heart disease that are stored in the database. These are:

* 'Major cardiovascular diseases (I00-I78)'
* '#Diseases of heart (I00-I09,I11,I13,I20-I51)'
* 'Acute rheumatic fever and chronic rheumatic heart diseases (I00-I09)'
* 'Hypertensive heart disease (I11)'
* 'Hypertensive heart and renal disease (I13)'
* 'Ischemic heart diseases (I20-I25)')
* 'Acute myocardial infarction (I21-I22)'
* 'Other acute ischemic heart diseases (I24)'
* 'Other forms of chronic ischemic heart disease (I20,I25)'
* 'Atherosclerotic cardiovascular disease, so described (I25.0)'
* 'All other forms of chronic ischemic heart disease (I20,I25.1-I25.9)'
* 'Other heart diseases (I26-I51)'
* 'Acute and subacute endocarditis (I33)'
* 'Diseases of pericardium and acute myocarditis (I30-I31,I40)'
* 'Heart failure (I50)'
* 'All other forms of heart disease (I26-I28,I34-I38,I42-I49,I51)'
* '#Essential hypertension and hypertensive renal disease (I10,I12,I15)'
* '#Cerebrovascular diseases (I60-I69)'
* '#Atherosclerosis (I70)'
* 'Other diseases of circulatory system (I71-I78)'
* '#Aortic aneurysm and dissection (I71)'
* 'Other diseases of arteries, arterioles and capillaries (I72-I78)'
* 'Other disorders of circulatory system (I80-I99)'

Note that a number of these contain multiple diseases ('Major Cardiovascular Diseases' for example); however this shouldn't have a major effect on the conclusions drawn. The full method is recorded in this [notebook](https://github.com/rvanderheyde/ThinkStats2/blob/master/code/report1.ipynb)

Results
-----------

The majority of the groupings of heart diseases show some amount of periodicity. For example, I plotted the data from the 'Major Cardiovascular Disease' group over time which looked like the figure below.

![image][chart3]

You can clearly see that the plot resembles the Influeza and Pneumonia one above. To find out what the major frequency component is, I created a plot of the power spectral density of the time series, which you can see below.

![image][chart4]

I removed the zero frequency component, because it represents a vertical shift, which dwarves the rest of the peaks on the PSD chart. The peak corresponds to a frequency of 3.17e-8 Hz, which comes out to a sample every 365 days or 1 year. Most of the other groupings have the same max frequency component as well; in fact all but the 'Other Acute Ischemic Heart Diseases,' 'Acute and Subacute Endocarditis,' and 'Other Disorders of Circulatory System' have a max frequency component at the frequency corresponding to a period of 1 year. 

Apparently, this is a known phenomenon. Auda Fares wrote an [article](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3662093/) titled "Winter Cardiovascular Disease Phenomenon" in the April 2013 edition of the North American Journal of Medicine synthesizing the literature on the phenomenon. Earlier, Dimitrios Seretakis; Pagona Lagiou, MD; Loren Lipworth, DSc; et al, wrote an [article](http://jama.jamanetwork.com/article.aspx?articleid=418241) in JAMA concerning the "Changing Seasonality of Mortality From Coronery Heart Disease" in September of 1997, so this is a well known phenomenon. Yet the exact cause of this hasn't been determined. Most suggest that it is some environmental effect, such as temperature or lack of physical activity, but this hasn't been proven fully. 

In the future, it might be interesting to examine some of the proposed causes for this phenomenon. 

[chart1]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown-3
[chart2]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown-4
[chart3]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown
[chart4]: https://github.com/rvanderheyde/ThinkStats2/blob/master/reports/Unknown-2
