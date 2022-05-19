# https://stackoverflow.com/questions/64167737/highlight-a-line-in-ggplot-with-multiple-lines
#https://stackoverflow.com/questions/59545834/highlighting-one-of-my-line-graphs-in-ggplot
library(tidyverse)    
# Data in wide format
df_wide <- data.frame(
    Horizons = seq(1,10,1),
    Country1 = c(2.5, 2.3, 2.2, 2.2, 2.1, 2.0, 1.7, 1.8, 1.7, 1.6),
    Country2 = c(3.5, 3.3, 3.2, 3.2, 3.1, 3.0, 3.7, 3.8, 3.7, 3.6),
    Country3 = c(1.5, 1.3, 1.2, 1.2, 1.1, 1.0, 0.7, 0.8, 0.7, 0.6)
)

# Convert to long format
df_long <- df_wide %>%
    gather(key = "variable", value = "value", -Horizons)

colors <- c(Country1 = "red", Country2 = "grey50", Country3 = "grey50")
sizes <- c(Country1 = 2, Country2 = .5, Country3 = .5)
# Plot the lines
plotstov <- ggplot(df_long, aes(x = Horizons, y = value)) + 
    geom_line(aes(colour = variable, size = variable, group = variable)) +
    scale_color_manual(values = colors) +
    scale_size_manual(values = sizes) +
    theme_bw()
plotstov

# different option
g <- ggplot(df_long, aes(x = Horizons, y = value)) + 
    geom_line(aes(colour = variable == "Country1", 
                  size = variable == "Country1", 
                  group = variable)) +
    scale_color_manual(name = "variable", labels = c("Other", "Country1"), values = c("grey50", "red")) +
    scale_size_manual(name = "variable", labels = c("Other", "Country1"), values = c(0.5, 2)) +
    theme_bw()

g
