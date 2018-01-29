# Data resources

### A list of helpful links and code for R, SQL, Python, HTML/CSS, etc. 

If you know of a good resource that you want to share, feel free to submit a pull request! If you're not sure how to do that, you can also submit an issue with the link to the resource and a quick intro to why it's helpful for you. 

This doc is based on my [google doc](https://docs.google.com/document/d/1dN9eeNJNaDIInpn7RCuigNL5NeBVkTFJxFtj8CkTW2g/edit?usp=sharing) of resources. I'm slowly working on coverting that file! 

## News

* [GovTech](http://www.govtech.com/) - articles about technology in government
* [Fivethirtyeight](http://fivethirtyeight.com/)
* [Upshot](https://www.nytimes.com/section/upshot) - NYT's data analysis 
* [Flowing Data](http://flowingdata.com/) - beautiful data visualization, both articles and tutorials 
* [HuffPost Data](http://data.huffingtonpost.com/)
* [WaPo Wonkblog](https://www.washingtonpost.com/news/wonk/?utm_term=.0c876ed1d11b)
* [Brookings](https://www.brookings.edu/)
* [Urban Institute data/viz](https://www.urban.org/data-viz)
* [NPR Political data and technology](https://www.npr.org/sections/political-data-technology)
* [LA Times data desk](http://www.latimes.com/local/datadesk/#nt=taxonomy-article)
* [The Guardian datablog](https://www.theguardian.com/data)


## GIS and online mapping

* [Carto](https://carto.com/)
* [Mapbox](https://www.mapbox.com/)
* [Modest maps](http://modestmaps.com/)
* [Leaflet JS](http://leafletjs.com/)
* [Stamen](https://stamen.com/maps/)

## Data visualization (mostly point-and-click)

* [Tableau public](https://public.tableau.com/s/) - Tableau desktop is **free** with a student email address! woohoo! 
* [Gephi](https://gephi.org/)
* [UMD treemap](http://www.cs.umd.edu/hcil/treemap/)
* [Chart.js](https://github.com/chartjs)
* [Raw graphs](http://rawgraphs.io/)
* [Timeline](https://timeline.knightlab.com/)

### General data viz books, etc. 

* [Data points: visualization that means something](http://flowingdata.com/data-points/) by Nathan Yau
* [Visualize this](http://book.flowingdata.com/) by Nathan Yau
* Anything by Edward Tufte
* [Designer's guide to creating charts and diagrams](https://www.amazon.com/Designers-Guide-Creating-Charts-Diagrams/dp/0823013383) by Nigel Holmes
* [Cool infographics](https://www.amazon.com/Cool-Infographics-Effective-Communication-Visualization/dp/1118582306) by Randy Krum
* [TED talk: The beauty of data visualization](https://www.ted.com/talks/david_mccandless_the_beauty_of_data_visualization?language=en) by David McCandless
* [The functional art](http://www.thefunctionalart.com/p/about-book.html) by Alberto Cairo

## R

### Links

* [awesome-R](https://github.com/qinwf/awesome-R) - github repo with SO MANY good R resources! Mostly packages, some other things at the end. 
* [RStudio online learning](https://www.rstudio.com/online-learning/)

#### Mentorship

* [Data helpers](https://www.datahelpers.org/) - A site by Angela Bassa with a list of people willing to help/mentor!

#### Podcasts

* [Dataframed](https://www.datacamp.com/community/podcast) - datacamp's podcast
* [Not so standard deviations](http://nssdeviations.com/)
* [Data skeptic](https://dataskeptic.com/)
* [Partially derivative](http://partiallyderivative.com/)
* [Linear digressions](http://lineardigressions.com/)


#### Interviews

* [.Rprofile Mara Averick](https://ropensci.org/blog/2017/11/10/rprofile-mara-averick/)
* [.Rprofile Karthik Ram](https://ropensci.org/blog/2018/01/12/rprofile-karthik-ram/)
* [.Rprofile Jenny Bryan](https://ropensci.org/blog/2017/12/08/rprofile-jenny-bryan/)

#### Packages to know/learn

* [ROpenSci packages](https://ropensci.org/packages/)
* [Emo: emojis in R](https://github.com/hadley/emo) because why not? 
* [Tidyverse packages](https://www.tidyverse.org/)
* [Broom](https://cran.r-project.org/web/packages/broom/vignettes/broom.html)- tidy model output
* [Markovify](https://github.com/abresler/markovifyR)- use this for future Markov chain poems! Re: Malcolm's [tweet](https://twitter.com/malco_bearhat/status/956593858573316096)

#### Blogs

#### Books

#### Style guides

### General

### Helpful file functions

```{r}
file.path() # takes folder names and returns a path to your file

file.choose() # pulls up finder so you can point to your file

download.file(url, dest_path) # makes downloading files reproducible
```

#### Extracting data from PDFs

ROpenSci has an awesome package to use tabula in R-- [tabulizer](https://github.com/ropensci/tabulizer)

[Tabula](http://tabula.technology/) is also awesome on its own. 

```{r}
# example code from github

library("tabulizer")
f <- system.file("examples", "data.pdf", package = "tabulizer")
out1 <- extract_tables(f)

out2 <- extract_tables(f, pages = 1, guess = FALSE, method = "data.frame")

extract_areas() # turns the pdf into an R graphic so you can select the tables on a page, if the whole page isn't a table! 

out3 <- extract_text(f, page = 3) # gets just the text from the table, without turning it into a dataframe
cat(out3, sep = "\n")
## len supp dose
## 4.2 VC 0.5
## 11.5 VC 0.5
## 7.3 VC 0.5
## 5.8 VC 0.5
## 6.4 VC 0.5
## 10.0 VC 0.5
## 11.2 VC 0.5
## 11.2 VC 0.5
## 5.2 VC 0.5
## 7.0 VC 0.5
## 16.5 VC 1.0
## 16.5 VC 1.0
## 15.2 VC 1.0
## 17.3 VC 1.0
## 22.5 VC 1.0
## 3
```

How to install tabulizer:

(On Windows) 

From github vignette:

In command prompt, install Chocolately if you don't already have it:

```
@powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin
```

Then install java! 

```
choco install jdk7 -y
```

To set an environment variable in R use

```
Sys.setenv(JAVA_HOME = "C:/Program Files/Java/jdk1.8.0_92")
```

if that doesn't work, look at the other options in the vignette. 

Then install the dev version of the package (not yet on CRAN) 

```{r}
if (!require("ghit")) {
    install.packages("ghit")
}
# on 64-bit Windows
ghit::install_github(c("ropensci/tabulizerjars", "ropensci/tabulizer"), INSTALL_opts = "--no-multiarch")
# elsewhere
ghit::install_github(c("ropensci/tabulizerjars", "ropensci/tabulizer"))
```

### Excel in R

[Using the xlsx package to create an excel file](https://www.r-bloggers.com/using-the-xlsx-package-to-create-an-excel-file/)

[readxl package](http://readxl.tidyverse.org/) - tidyverse w/ excel

```{r}
excel_sheets() # gives a character vector of the sheet names

read_excel() # reads in excel files
# args: sheets (defines which sheet you want)
        col_names = TRUE
        col_types ("blank" to skip a column)
        skip (n rows to skip)

# put all sheets in a list to keep them together

my_workbook <- lapply(excel_sheets("data.xlsx"),
  read_excel,
  path = "data.xlsx")
```

[XLConnect](https://www.rdocumentation.org/packages/XLConnect/versions/0.2-13) - dynamic connection between R and excel. 

```{r}
createSheet(book, “name”)
loadWorkbook(“path”)
getSheets(book)
writeWorksheet () # function (object, data, sheet, startRow = 1, startCol = 1, header = TRUE, 
    rownames = NULL) 
writeWorkbook(object, “path”)
renameSheet() # function (object, sheet, newName) 
removeSheet() # function (object, sheet) 
```


### Googlesheets package <3

[googlesheets](https://github.com/jennybc/googlesheets)

There's a [vignette](https://rawgit.com/jennybc/googlesheets/master/vignettes/basic-usage.html) with lots of good info. 

```{r}
# uses oauth to access drive

gs_auth() # run to authorize
```

From the github site, an overview of the functions:

```{r}
gs_ls() # list sheets
gs_title() # register a sheet by title
gs_key() # register a sheet by key
gs_url() # register a sheet by url

... tbd 
```

### Dates and times

### Dataframes/tables

### Conditionals

### ggplot2

[ggplot2 gallery](http://r-statistics.co/Top50-Ggplot2-Visualizations-MasterList-R-Code.html) 

How to change the order of the bars in `geom_bar()` !!!!

```{r}
# from https://stackoverflow.com/questions/5208679/order-bars-in-ggplot2-bar-graph

require(forcats)

ggplot(data, aes(x = fct_infreq(var))) + geom_bar()

# from https://rstudio-pubs-static.s3.amazonaws.com/7433_4537ea5073dc4162950abb715f513469.html

x$name <- factor(x$name, levels = x$name[order(x$val)])
ggplot(x, aes(x = name, y = val)) + theme_bw() + geom_bar(stat = "identity")
```

### GIS in R

[GIS in R](http://www.nickeubank.com/gis-in-r/) by Nick Eubank. 

[Robin Lovelace: Creating maps in R](https://github.com/Robinlovelace/Creating-maps-in-R)

[R Spatial](http://rspatial.org/index.html)

For geocoding, try [opencage](https://ropensci.org/tutorials/opencage_tutorial/) per Maelle's suggestion! 

```{r}
# forward geocoding

output <- opencage_forward(placename = "Sarzeau")

# reverse geocoding

output2 <- opencage_reverse(latitude = 51.5034070,
                            longitude = -0.1275920)
                            
# adding parameters

results3 <- opencage_forward(placename = "Berlin", country = "DE")
```

But for now, I'm using a function I found online. Example:

I wanted to geocode the locations of the Boston community centers recently. I found the names [here](https://www.boston.gov/community-centers). Using the chrome extension for [CSS selector gadget](http://selectorgadget.com/), I scraped the names into R.

```{r}
community_centers_url <- read_html("https://www.boston.gov/community-centers") # site with names

centers <- community_centers_url %>%
  html_nodes(".cd-t") %>% # css selector
  html_text() # I want the text
```

Then I used a combination of functions to geocode. 

```{r}
url <- function(address, return.call = "json", sensor = "false") {
 root <- "http://maps.google.com/maps/api/geocode/"
 u <- paste(root, return.call, "?address=", address, "&sensor=", sensor, sep = "")
 return(URLencode(u))
} # calling google maps API
 
geoCode <- function(address,verbose=FALSE) {
 if(verbose) cat(address,"\n")
 u <- url(address)
 doc <- getURL(u)
 x <- fromJSON(doc,simplify = FALSE)
 if(x$status=="OK") {
 lat <- x$results[[1]]$geometry$location$lat
 lng <- x$results[[1]]$geometry$location$lng
 location_type <- x$results[[1]]$geometry$location_type
 formatted_address <- x$results[[1]]$formatted_address
 return(c(lat, lng, location_type, formatted_address))
 } else {
 return(c(NA,NA,NA, NA))
 } 
} # actually getting the addresses
```

I'm sure there's a cleaner way to do this, I'll work on using opencage and then updating this page!


#### Census data! I love census data!

[Tidycensus](https://github.com/walkerke/tidycensus) for demographic data. 

```{r}
# median income in Boston census tracts

bos_inc <- get_acs(geography = "tract", 
              variables = c(medincome = "B19013_001"), 
              state = "MA",
              county = "Suffolk")

# see available variables for 2016 acs 5-year

load_variables(year = 2016, dataset = "acs5")
```

[Tigris](https://github.com/walkerke/tigris) to load the shapefiles to map census data!

```{r}
options(tigris_use_cache = TRUE) # doesn't cache by default
bos_tract <- tracts(state = "MA", county = "Suffolk")
```

You can join the two with `tigris::geo_join`. Regular joins don't work with spatial data. 

```{r}
bos_joined <- geo_join(bos_tract, bos_inc, by = "GEOID")
```

And if I want to exclude a particular tract (it's mostly water, NA for all demographics) and makes my maps looks ugly :(

```{r}
bos_joined <- subset(bos_joined, NAME.1 != "Census Tract 9901.01, Suffolk County, Massachusetts")
```

`dplyr::filter` doesn't work with spatial data!! 
---

* Python

* HTML/CSS

* Data sources

* Regex

* SQL

* Jekyll + blogging

* General tips + tricks
