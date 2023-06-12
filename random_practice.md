# R Practice and Understanding the Basics
================
Amanda Boyers
2023-06-12

### Creating a vector (R)- a group of data elements of the same type stored in a sequence in R
The combine function creates a vector.

```{r vector for data}
x <- c(1,3,5)
```

The names() function in R is used to get or set the name of an object. The object can be a list, vector, matrix, and 
DataFrame. Use names(x) to get the name of the object and names(x) <- vector to assign names to the object. To remove 
the object name assign the value NULL

```{r names}
names(x)<- c("a","b","c")
x
```

Vectors are ATOMIC or LIST
<img src="figures/vector.png" width="80%" />
<img src="../../figures/vector.png" style="display: block; margin: auto;" />
![](../figures/vector.png)

```{r names}
list("a", 1L, 1.5, TRUE)
str(list("a", 1L, 1.5, TRUE))
list('Chicago' = 1, 'New York' = 2, 'Los Angeles' = 3)
```
### Working with dates
```{r names}
library(lubridate)
today()
now()
ymd(20210120)
as_date(now())
```
### Creating a data frame

```{r putting vectors together to make a data frame}
data.frame(x = c(1, 2, 3) , y = c(1.5, 5.5, 7.5))
```
### Making folders and files

```{r creating directories and files}
dir.create ("destination_folder")
file.create (“file.cvs”, “destination_folder”)
file.create("file.cvs")
file.create("file.txt")
```
### and then deleting them

```{r deleting}
unlink("file.txt")
```

## Matrices
### Matrix- a 2-D collection of data elements, can only contain 1 type of data
### Vector- a 1-D sequence of data elements

```{r matrix}
matrix(c(3:8), nrow = 2)
```

```{r }
print("syntax")
Print(syntax)
Print("syntax")
```
## Transforming data

```{r transform}
yearend_sales <- midyear_sales * 2
yearend_sales
Solar.R > 150 & Wind > 10
```

## Tidyverse

```{r Tidyverse}
install.packages(pkgs, lib, repos = getOption("repos"),
                 contriburl = contrib.url(repos, type),
                 method, available = NULL, destdir = NULL,
                 dependencies = NA, type = getOption("pkgType"),
                 configure.args = getOption("configure.args"),
                 configure.vars = getOption("configure.vars"),
                 clean = FALSE, Ncpus = getOption("Ncpus", 1L),
                 verbose = getOption("verbose"),
                 libs_only = FALSE, INSTALL_opts, quiet = FALSE,
                 keep_outputs = FALSE)
install.packages("styler")
install.packages("tidyverse")
str(diamonds)
library(tidyverse)
```
## Previewing data and understanding functions

```{r previewing}
browseVignettes("ggplot2")
data("diamonds")
View(diamonds)
colnames(diamonds)
head(diamonds)

## Transforming data

```{r mutate}
mutate(diamonds, carat_2=carat*100)
print(diamonds, n=11)
colnames(diamonds)
mutate(diamonds, carat_2=carat*100)
```
Preview more data

```{r previewing}
as_tibble(diamonds)
data()
data("mtcars")
mtcars

##creating data frame by reading CSV files

```{r previewing}
read_csv(readr_example("mtcars.csv"))
(readr_example("mtcars.csv"))
```
```{r}
library(readxl)
readxl_example()
read_excel(readxl_example("type-me.xlsx"))
excel_sheets(readxl_example("type-me.xlsx"))
read_excel(readxl_example("type-me.xlsx"), sheet = "numeric_coercion")
install.packages("here")
library(here)
install.packages("skimr")
library("skimr")
install.packages("janitor")
library("janitor")
install.packages("dplyr")
library("dplyr")
install.packages("palmerpenguins")
library("palmerpenguins")
```

```{r }
skim_without_charts(penguins)
glimpse(penguins)
head(penguins)
```
## Working with Pipes 

```{r pipes}
penguins %>% 
  select(-species) %>% 
  rename(island_new=island)
```

```{r}
rename_with(penguins, tolower)
clean_names(penguins)

penguins %>% arrange(bill_length_mm)
penguins %>%  arrange(-bill_length_mm)
penguins2 <- penguins %>%  arrange(-bill_length_mm)
View(penguins2)

penguins %>% 
  group_by(island) %>%
  drop_na() %>% 
  summarize(mean_bill_lengh_mm = mean(bill_length_mm))

penguins %>% 
  group_by(island) %>%
  drop_na() %>% 
  summarize(max_bill_length = max(bill_length_mm))

penguins %>% 
  group_by(species, island) %>%
  drop_na() %>% 
  summarize(max_bill_length = max(bill_length_mm),mean_bill_lengh_mm = mean(bill_length_mm))

penguins %>% 
  filter(species == "Adelie")
  ```
