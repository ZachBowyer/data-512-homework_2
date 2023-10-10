# data-512-homework_2
Zachary Bowyer
10/10/2023
University Of Washington
Data 512

# Goal of the project
???

# License of wikipedia data
Wikipedia's text content, in a nutshell, can be used under the terms of the Creative Commons
Attribution Share-Alike license (CC-BY-SA); unless otherwise indicated, it can also be used
under the terms of the GNU Free Documentation License. The global terms of use dictate the ways
content from Wikimedia sites can be properly attributed when used under the CC-BY-SA license. 
See: https://en.wikipedia.org/wiki/Wikipedia:Reusing_Wikipedia_content for more details

# License of part of the software
Some code, which is properly referenced in it's respective location
was developed by Dr. David W. McDonald for use in DATA 512, a course in the UW MS Data Science degree program. This code is provided under the Creative Commons CC-BY
license. Revision 1.2 - August 14, 2023. Some of the original code made be modified, however it still falls under the Creative Commons license.

# How to reproduce the analysis
Install anaconda
Install packages from environment.yml
Create jupyter kernel from conda env
Run jupyter
run cells

# All file and descriptions

# Notes for researchers
The API takes a long time to run. This could be improved by serving bulk requests instead of one at a time. 

# Research implications

## What I've learned/found 
Throughout the course of this assignment, I've learned quite a few things. 
First, I learned through one of the example notebooks that I should probably 
use environment variables to mask credentials rather than an ignored text file 
due to the risk involved with the text file accidently being pushed later. Next, 
I have learned in doing this assignment that there not only exists a wikipedia framework
for assigning scores to articles, but there is also a machine learning model that 
can automatically score them. Also, of course I've learned that I should be using Pandas
more often than not for these types of problems, as while I typically like to stick with
either pure lists or dictionaries, programming counts and groupby's manually becomes too tedious.
Finally, I've learned/reinforced that free API resources often take a long time to return results.  
One thing that suprised me about my findings is that states with small 
relative populations like Vermont, Maine, and Alaska had the highest number of wikipedia articles
about them. My assumption here is that this simply is due to the large number of towns relative 
to population in those states.

## What theories I have about why any biases might exist
There are a few possible reason for biases in this assignment. First being that the number of 
towns/cities in a state probably isn't influenced much by population alone, and may be more influenced
by land mass and other variables. What this means is that we can't expect to be suprised by the results 
we have not aligning up with population count, for example. Additionally, another bias that could exist here
is that states with a better education system and more technology may be more likely to produce articles with 
good scores. Finally, while Washington DC is not a state, I can see it retracting a non-trivial portion of the 
population count from Maryland and Virginia, which may affect their results. 

## Reflections to share about the process of the assignment
Overall I thought the assignment was a good one. One thing that really suprised me was how long it took to run 
the apis on roughly twenty-thousand rows (4.5 hours). Besides that, the instructions were clear and I was able
to implement the directions quite well. I think ending the assignment with a reflection section makes sense and
it actually forced me to think a little bit more about trying to interpret the results of my analysis. 

## Question response 1: What biases did you expect to find in the data (before you started working with it), and why?
Before working with this data, one major bias, which I have already touched on above is that the per-capita article
quality counts on a state-basis and divisional-basis are biased because it's possible that population centers likely have
better scores, as more editors have probably looked at them. This means that states with more population centers may have
a higher capita of quality articles simple due to having topics more people care about. 
Another source of bias I noticed is that we are using a list of cities from 2023 while using the population count from 2022. 
These should be the same year to minimize the risk of not having new cities accounted for in the analysis. 

## Question response 2: What (potential) sources of bias did you discover in the course of your data processing and analysis?
One potential source of bias I found in my analysis is that the ORES predictor may be inherently biased for any number of reasons
due to it being a machine learning algorithm. For example, perhaps ORES uses something as simple as number of pictures, length of 
article, and the inverse of the number of grammatical mistakes to choose it's score. At the time of the analysis (and even know) 
I still am not familiar with the mechanism which ORES operates. Another potential source of bias I discovered is that using only the number
of city articles to try to show coverage of cities on wikipedia per state doesn't take into account the fact that articles could be 1 line long.
For example, I could probably spend an afternoon making one sentence article about every single town in Washington state.

## Question response 3: How might a researcher supplement or transform this dataset to potentially correct for the limitations/biases you observed?
One thing a reasearcher could do to correct for biases is to first make sure that all data is from the same years. For example, both the 
article dataset and the census dataset should be from the same year. Another thing a researcher could do to correct for bias is to look into whether
there is a correlation between cities with high population counts and ORES scores. If this relationship exist, the researcher may need to consider adjusting for 
this. Finally, I'd suggest a researcher should look into article lengths, as 'coverage' between states is vaguely defined and weights long and short articles similarly. 