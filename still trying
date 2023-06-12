# Penguin Plots: Practice analysis

## Setting up my environment

### Packages used: 'tidyverse', 'palmerpenguins', 'ggplot2'
Notes: setting up my *R* environment by loading the **'tidyverse','palmerpenguins' and 'ggplot2'** packages:
```{r}
install.packages("tidyverse")
library(tidyverse)
library(ggplot2)

install.packages("palmerpenguins")
library(palmerpenguins)

```

## Previewing the data and transforming it
Apparently, ending this line with two spaces will start a new paragraph.   Did it work?
```{r}
head(penguins)

penguins %>% 
  mutate(body_mass_kg = body_mass_g/1000, 
         flipper_length_m = flipper_length_mm/1000)
```

##Penguin Plots
As this plot demonstrates, flipper length and body mass have a positive correlation.  The bigger the penguin, the longer the flipper length.
```{r}

ggplot(data=penguins, aes(x=flipper_length_mm, y = body_mass_g))+
  geom_point(aes(color=species))+
  facet_wrap(~species)

ggplot(data = penguins) + geom_point(mapping = aes(x = flipper_length_mm, y = body_mass_g))

```
