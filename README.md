## How to Operationalize Spatial Variables for Econometric (Hedonic) Analysis

Suppose you have a dataset of apartment data. Each row is a building and each building has various attributes that describe it. These might include average rent, the number of units, how many stories, what year it was built, whether there is an elevator or not.
The list of possibilities goes on. Say you were a real estate developer--you might want to know which attributes of a building contribute to higher rent. With this information you could, in theory, include those features in your next project and acheive higher rents.

This question is often asked in economics as well. The approach taken is called hedonic valuation. In short, we take a value or price of something (often land) and try to model that value as a function of its related characteristics, often using a multivariate regression.
In economics this is commonly used for nonmarket valuation of externalities whose impacts are hard to measure. For example, take two houses: everything about them is identical except one is located near a superfund site and the other is not. The difference in prices reflects
the negative externality of the pollution in a dollar amount. 

Back to our building example. With the given data, organized into observations of buildlings we could try to describe average rent as function of the other attributes such as:


<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;rent&space;=&space;\beta_0&space;&plus;&space;\beta_1(num&space;units)&space;&plus;&space;\beta_2(num&space;floors)&space;&plus;&space;\beta_3(year&space;built)&space;&plus;&space;...&space;&plus;&space;\epsilon" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;rent&space;=&space;\beta_0&space;&plus;&space;\beta_1(num&space;units)&space;&plus;&space;\beta_2(num&space;floors)&space;&plus;&space;\beta_3(year&space;built)&space;&plus;&space;...&space;&plus;&space;\epsilon" title="rent = \beta_0 + \beta_1(num units) + \beta_2(num floors) + \beta_3(year built) + ... + \epsilon" /></a>

But suppose, like the superfund site example, we want to include environmental/geographic attributes of the building? These notebooks give an example of how this might be approached.


There are three notebooks that should be run in the following order:

1. `props_to_shape` which simply converts lat lon points to a shapefile
2. `osm` which calls collects data from the open street maps api about area amenities that might be important
> <http://wiki.openstreetmap.org/wiki/Overpass_API>

> <https://taginfo.openstreetmap.org/>

3. `spatial_work` which uses `pandana`, `geopandas` and `shapely` to compute the aggregate spatial statistics for each building
> <https://github.com/UDST/pandana>

> <http://geopandas.org/>

> <https://toblerity.org/shapely/manual.html>
