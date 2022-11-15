---
title: 'Finding the Best Burrito in Philadelphia'
date: 2022-11-14
author: Adam & Shreya
permalink: /posts/2022/11/best-burrito-philly/
---

### Introduction
We moved to Philly in August 2021, and immediately noticed the glaring lack of good Mexican food within walking distance of Penn. Having both done our undergrad in Los Angeles, we would rarely have to walk more than 2 blocks to get our hands on a top tier burrito.

And so, we began our quest to find the best burrito in Philly. After over a year of searching and disappointment - and an obscene amount of rice and beans - we were able to identify a few burritos that didn’t make us regret moving across the country for grad school.
	
As researchers, we believe in open sourcing our findings, so here is everything we learned on our journey as 2 Californians desperately trying to find a good burrito on the east coast.

  

### Methods
We decided to formulate the search for the best Philly burrito as the following optimization problem:

$$
\begin{aligned}
\min_x\quad & L(x)\\
\text{s.t.}\quad & x\in \text{PhillyBurritoJoints}
\end{aligned}
$$

Where we define PhillyBurritoJoints and the set of all burrito offering facilities and L as the inverse goodness of the output burrito of the facility evaluated across 5 dimensions: cost, speed, tortilla quality, fillings, salsa, and overall experience. This gives us our final formula for inverse goodness:

$$
\begin{aligned}
L(x) &= (1-\text{monetary_cost}(x))\\
&+ \text{speed}(x)\\
&+ \text{tortilla_quality}(x)\\
&+ \text{filling_quality}(x)\\
&+ \text{salsa}(x)\\
&+ \text{overall}(x)\\
&+ 7
\end{aligned}
$$

We add the final 7 for good luck.

To evaluate L for each x, we manually rated each burrito we consumed on a scale of 1-10 for each of these dimensions, and calculated the total goodness of the burrito as the sum of the sub-goodness scores of each dimension. Even though the burrito restaurants are quite sparse in Philly, we decided to not evaluate over all burrito restaurants due to computational resource limitations, financial constraints, and general lack of time. Instead, we performed a highly nonrandom sampling from PhillyBurritoJoints by choosing places with high Yelp ratings, positive reviews from friends, or high geographical convenience.

The chosen establishments:
-   Sailor Christy’s: A food truck by UPenn [Walnut and 38th
-   Rosy’s Taco Bar: A restaurant right by Shreya’s house [Walnut and 24th]
-   Tacos don Memo: A food truck by UPenn [Spruce and 38th]    
-   Jackass Burrito: a pop-up ghost kitchen operating out of El Rey [Chestnut & 20th]    
-   Cafe Ynez: A restaurant right by Adam’s house [Washington and 21st]    
-   Los Gallos: A restaurant in South Philly [Wolf and 10th]
  
### Experiments

At each establishment, we sampled a vegetarian burrito and a chicken burrito and rated each separately across all dimensions. Our final score for each dimension was the average between the two burritos we tried. After checking for correlation, we generally found that the goodness of a vegetarian burrito was reflected by meat burritos as well, so we feel our assigned scores reflect the overall burrito potential of each establishment in PhillyBurritoJoints.


| **Establishment** | **Cost** | **Speed** | **Tortilla** | **Filling** | **Salsa** | **Overall Experience** | **Good Luck** |
|-------------------|----------|-----------|--------------|-------------|-----------|------------------------|---------------|
| Sailor Christy's  | $9       | 5         | 6            | 7           | 6         | 4.5                    | 7             |
| Rosy's Taco Bar   | $15      | 4         | 6            | 3           | 3         | 5.5                    | 7             |
| Tacos don Memo    | $10      | 5         | 7            | 8           | 7.5       | 8                      | 7             |
| Jackass Burrito   | $12      | 9         | 5            | 7           | 5         | 7.5                    | 7             |
| Cafe Ynez         | $14      | 6         | 3            | 2           | 8         | 5                      | 7             |
| Los Gallos        | $11      | 4         | 7            | 8           | 9         | 7                      | 7             |


Table 1. All the data, evaluate it yourself.


| **Establishment** | **$-L(x)$** |
|-------------------|-------------|
| Tacos don Memo    | 42.5        |
| Los Gallos        | 42          |
| Jackass Burrito   | 40.5        |
| Sailor Christy's  | 35.3        |
| Cafe Ynez         | 31          |
| Rosy's Taco Bar   | 28.5        |


Table 2. Ok fine, we did some evaluation. Ranked by decreasing goodness.

### Conclusion
In conclusion, our analysis shows that the best burrito is from Tacos don Memo. It was a delicious, reasonably priced burrito, and we highly recommend any readers in Philly to go there at their earliest convenience. Though we still deeply miss California Mexican food, spending the next 4 years of our life here doesn’t seem as bad as it once did. For future work, we plan to also identify the best cappuccino in Philly - please let us know some good places to start our search :)
