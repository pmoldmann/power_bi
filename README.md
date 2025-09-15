# power_bi
Examples for the design of power bi reports and semantic models

# about me
I am a freelance power bi consultant located in Aachen, Germany (https://paulmoldmann.de).

# motivation
I love Power BI and want to share with others how I do things - just as I have profitted from what other professionals out there have done.

# Sections

In the report wind_power_germany_development you will find a semantic model and report pages that implement the approaches that are described here or are snippeted in the folders found in this repo. So feel free to download the semantic model to find out more.
Features:
- Anomaly / Outlier Detection (see description below)
- deneb visual to compare two measures (see also https://github.com/pmoldmann/deneb_examples/tree/main/Two_Measure_Compare)
- measure slicer (use a slicer to select a measure that is then used on a report page)
- drill through page with action button
- Help Page and navigation using a standard header (that also holds drop down slicers)

Here is a screenshot for the total development of installed capacity in 2024:<br>
![Wind Power Germany Development](wind_power_germany_development.png)
<br>

## DAX

### Outlier Detection (max_outlier_zscore.dax)
You might know the problem when working with big semantic models (in my last case > 100M rows in several fact tables) that from time to time, some rows have corrupted data. This data severely minimizes your data quality when aggregating (summing) over these fact tables. 
But... how to find this corrupted data? 
Lately I got tired of seaching again manually and tried out several approaches. 
But the anomaly detection that is built in power bi is too slow and also clumsy to use.
Then I looked in the web for alternative solutions but didn't find any that I really liked. Then I came across the z-score (https://en.wikipedia.org/wiki/Standard_score) and implemented this approach as a calculation item in power bi. 
It works like a charm, even for > 100M rows and several dimensions. 

## Powerquery

### Date Dimension (date_dimension.m)
I have derived my own version from the great date table designed by <nolockcz> (https://github.com/nolockcz/PowerQuery/tree/master/Date%20Dimension)


## TMDL

### Time Intellgence measures as calculation group (calculation_group.tmdl)
Here you can find the collection of time intelligence measures that I use as basis in my projects. 