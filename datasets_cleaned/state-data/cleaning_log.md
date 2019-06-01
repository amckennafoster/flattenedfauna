# Dataset:VTRoadkillData_1971-2006

## Original download: https://catalog.data.gov/dataset/vt-vehicle-animal-collisions-2006

Removed observations that do not include Latitude Longitude data. It would be possible to extrapolate latitude and longitude from highways, mile markers, but the choice was made to eliminate this data. 

Removed observations where the animal was living, eg. “mother and young one crossing the road.”

Removed observations that did not identify an animal.

Corrected spellings, Otter changed to Other, because comment field identified animal as raccoon. Standardized spelling and capitalization as much as possible, esp in the animal fields. Did not correct spellings of town, city, or street names, as I don’t know VT enough to make these judgement calls. 

Normalized identities to prioritize animal name, eg. “Dead skunk” changed to “Skunk dead.”

Removed special character--F&W changed to FW. 

Standardized all dates to ISO 8601  YYYY-MM-DD

Changed F&W to FW to remove special character

Filled blank text cells with NULL and blank numeric with -9999. Note that several MM cells were filled as 0, 

Consider that this data goes back as far as 1971, and highways, townships will have changed since then. 

Note: No information about what “MSRI code” is, but it seems to describe the type of animal. 

Normalize and define abbreviations.
AOT= Agency of transportation
F&W = Fish and wildlife, changed to FW

