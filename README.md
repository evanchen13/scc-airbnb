# Santa Clara County Airbnb Investigation

[Airbnb](https://www.airbnb.com/), founded in 2008, is an online platform that allows property owners to market short-term rentals to guests. The company's original intention was to follow a sharing economy model in which hosts would only occasionally rent out their spaces. However, there have been concerns in recent years that owners are listing their properties permanently, more like hotels, which is against the law in many locations and could lead to a number of downstream consequences such as gentrification and lack of affordable housing. Airbnbs that operate like hotels are also able to avoid certain taxes and regulations that other regular hotels must endure.

I was curious to see the effects of Airbnb in Santa Clara County, which is where I live. As a result, I have downloaded data from [Inside Airbnb](http://insideairbnb.com/index.html) on all 5,185 listings within the county, as of October 25, 2020. In this analysis, I answer the following questions:

- How often are Airbnb listings occupied?
- Do Airbnbs generate more income per month than long-term rentals?
- What percentage of listings have a host that lives in a different city than the listing location?
- How many listings do hosts tend to have?
- What features best predict how many listings a host has?

# Requirements

- Jupyter Notebook
- Numpy
- Pandas
- Matplotlib
- Seaborn
- re
- Datetime
- Sklearn

# Files in This Repository

- [scc-airbnb.ipynb](https://github.com/evanchen13/scc-airbnb/blob/main/scc-airbnb.ipynb) - Jupyter Notebook containing the code for this analysis
- [listings.csv](https://github.com/evanchen13/scc-airbnb/blob/main/listings.csv) - CSV file containing all data on Airbnb listings in Santa Clara County
- [base.yaml](https://github.com/evanchen13/scc-airbnb/blob/main/base.yaml) - environment YAML file containing the environment that I used to perform this analysis

To get the Jupyter Notebook running, execute the following in the command line and select `scc-airbnb.ipynb` from the Jupyter Notebook dashboard. The conda environment setup is optional.

```
$ git clone https://github.com/evanchen13/scc-airbnb.git
$ cd scc-airbnb
$ conda env create -f base.yaml
$ jupyter notebook
```

# Results

## How often are Airbnb listings occupied?

Using Inside Airbnb's San Francisco Model, the distribution for Airbnb occupancy hits a peak at around 5% and then gradually decreases until it reaches the maximum of 70%, at which point the number of listings shoots up. In fact, about 17% of all operating Airbnbs are at this maximum. This is likely due to the model being capped at 70%, so any listings that might have had higher occupancy were still adjusted down to make the model reasonable and conservative. Additionally, the occupancy distribution differs between various room types. Entire homes/apartments have the highest occupancy, followed by private rooms and then shared rooms.

## Do Airbnbs generate more income per month than long-term rentals?

Among all listings, the median Airbnb income per month is lower than the median Santa Clara County monthly long-term rent of $2,392. However, if the listings are narrowed down to those that are booked for at least one-third of the year, the median Airbnb income per month for entire homes/apartments becomes about equivalent to the median long-term rent. This threshold of one-third of the year is not unreasonably difficult to attain, given that around 40% of listings are able to. Of course, the number of people that a property accommodates also matters -- for entire homes/apartments, only those that accommodate at least four people and reach the one-third year threshold have a median higher than the median long-term rent.

## What percentage of listings have a host that lives in a different city than the listing location?

After narrowing down the dataset to records that have definitive host and property locations, I found that about 41% of listings have a host that lives in a different city than the listing location. Interestingly, many of the cities with higher amounts of Airbnb properties also have lower percentages of listings with hosts in the same city.

## How many listings do hosts tend to have?

About 31% of hosts have more than one listing and for those that have multiple, most have less than five. However, the maximum number of listings for a single host is 252, and many of the top property owners seem to be companies rather than individuals.

## What features best predict how many listings a host has?

The types of amenities a listing has, the types of verifications the host has, the response time and rate of the host, and the proportion of entire homes/apartments and private rooms owned by the host best predict the number of properties a listing's host has.

# Acknowledgements

Special thanks to [Inside Airbnb](http://insideairbnb.com/index.html) for providing the data, background information, and methodology for the San Francisco Model.

# License

The contents of this repository are covered under the [GNU General Public License v3.0](https://github.com/evanchen13/scc-airbnb/blob/main/LICENSE).
