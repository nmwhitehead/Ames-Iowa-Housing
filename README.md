# HOUSE PRICE FACTORS FOR AMES, IOWA


We were given a large amount of numerical and categorical data that had varying degrees of effect on the Sales Price of the homes in the great city of Ames, Iowa and are going to look at the importance of varying factors.


## Unsurpringly, squarefootage of varying floors were amoung the most important features


Ground living area, Garage area, 1st floot square footage, and basement square footate were all in the top 6 highest correlations with price.

To add to that, the intersection of price and 1st floor area proved to be one of the most important features.
A large house with street parking may sell for a large amount less than a medius sized house that can fit 2 cars in its garage.

## Even with the added intersection feature, overall quality of home is clearest factor


Overall Quality is a 1 to 10 ranking system that judges home quality using a system of measurement that I was not provided.

The correlation betwen quality and price is extremely clear in 4/10 through 8/10, where there are large clumps that can easily be fit with a straight line. There are obviously outliers, but with a dataframe this size, finding a line that clear is rare.

When we get up to 9/10 and 10/10 though, this pattern changes. There are no longer price clumps. The price is still more on average than the previous numbers, but the importance of quality to price decreeses.

The reason for this is that for people buying homes of that quality, the home being high quality is dissatisfier, not a satisfier.

For the non business folk in the room, a satisfier is something that you appreciater. If you've got a car guy that washes your car real quick every time you pay him to change your gas, you'd probably really appreciate that. You might not mind his schedule being a little less convinient than the other car guy, or paying a few extra dollars, because he does a little more than is required, and that's cool.

A dissatisfier is more of an expectation that you barely even think about. If the bar you go to give you your beer cold, you're not going to be super happy about it. You're not going to want to pay extra because that bar knows how to use refridgeration. But if that bar gives you warm beer, you're just never going to go there again.

So home buyers who consider home quality to be a dissatisfier aren't looking at the hom qualities of 9 or 10 as bonuses or reasons to pay more. They just aren't looking at any other homes, and are judging the price bassed entirely on other features.


# In the end, I narrowed it down to around 50 factors


Important factors used ended up being about what most people would expect.

Area, Quality, Year Built, number of Bathrooms, Open Porch Squarefootage, Air Conditioning, area of or lack of Masonry Veneer, Kitchen Quality, etc.

Most neighborhoods had little to no correlation with sale price, but some had positive or negative effects significant enough to factor in, and the neighborhoos of Northridge Heights had a ver large positive correlation.




###  When we look at the historgram of the residuals, they seem to be pretty noramally distributed


Using the basic Linear Regression transformation, we find the residuals to have a fairly normal spread, with the exception being the outlyer far to the left.

A normal spread around zero for residuals is what we want.

The mean of -349.32 isn’t exactly at 0, but not far off considering we are dealing with numbers in the hundreds of thousands.




### The graph of residuals against predicted values is unfortunately not as good


The predicted vs residual scatterplot is clearly heteroskedastic.

The conular shape is clear, even when the outlier in the bottom right isn’t factored in.

The lack of equality of residuals unfortunately makes it a less than ideal predictions method.




### The heavy right skewness in price may be a factor in this error.


Since there are fewer buyers of heavily expensive home, but the home prices go out so far to the right, it's hard to factor in their wants and needs when buying a home.




### The dissatisfier factor is likely the biggest issue for these expensive homes.


When we go back to the overall home quality, we can see that same heteroskedastic trend that we saw with residuals.

While factors like quality of home matter a lot to the people spending $100k to $300k on their home, as the homes get more expensive, these factors become expectations instead of icing on the cake. This dissatisfier mind set most likely also effects how they view features like a third full bath or the availability of air conditioning. They aren't willing to pay more for these features because these are expectations.

The problem this causes for the graph is that it causes the equation that factors in these data points to overestimate how much these people are willing to pay for their home.

This is made more visable when we graph the residuals against actual price. $300,00 is about the point that the graph begins overestimating the price by more and more.

The solution to this would be to judge the high quality, 9/10 and 10/10, homes as seperate from the remainders. That is unfortunately beyond my current skill level with data science.
