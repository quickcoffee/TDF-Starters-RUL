# TDF Starters Remaining-Useful-Life (RUL)

## Intro
This little project uses a neural network with LSTM-cells to predict the career end of Tour de France starters.  
To train the network, data about Tour de France starters between 1995 to 2019 from the excellent ressource https://www.procyclingstats.com has been scraped. The scraped data was then brought into the long-format and some features such as a cumulative count of years riding for a WorldTour/ProContinental/Continental-Team have been added. This data was then fed into a rather simple neural network with two layers of LSTM cells and a dense output layer with one cell and a linear activation function. The final model resulted in a RMSE of 2.426 and R2 of 0.742.
The data can be found on Kaggle: https://www.kaggle.com/lukassteger/career-statistics-tdf-starters-19952019
The model therefore gives a rough estimate on when a rider will end his career, but should also be seen in the light of the project's weaknesses: Data quality could be enhanced, as riders with breaks in their careers such as doping-bans or being with out a contract are included in the dataset. Also features such as height or weight, were not included due to missing data. Further, the integration of non-time varying variables could be done via a multi-input network architecture. The network's hyperparameters and the number of features could be enhanced in the future, in order to obtain better results.
Inspirations for this project were taken from RUL-projects such as https://github.com/gm-spacagna/deep-ttf/ and https://github.com/LahiruJayasinghe/RUL-Net
Another way to approach is project is to take it as a classification problem (eg. Is rider XY still active in 5 years? Yes/No) rather than a regression problem.
Unfortunately does Github not support the ipywidgets and in order to interactively explore the model's results it need to be opened as a Jupyter notebook.

## Results
Fist let's have a look at the scraped and tranformed data:  
  
There are 1358 riders in the dataset, 890 of those are retired and 468 are still considered as active.

![retired_active](https://github.com/quickcoffee/TDF-Starters-RUL/blob/master/plots/active_retired.png?raw=true "Retired vs. Active riders")

Looking only at the career length of the retired riders, the average career length is `13.8`:
![Career Length](https://github.com/quickcoffee/TDF-Starters-RUL/blob/master/plots/career-length.png?raw=true "Career Length")

The predictions of the trained model are reasonable and give a rough estimate of a rider's career.  
Scatterplot of the test set:  
![scatter_plot](https://github.com/quickcoffee/TDF-Starters-RUL/blob/master/plots/scatter_test.png?raw=true "Scatter Plot True vs. Predicted")

And a two examples of the results on a rider level:  
**Peter Sagan**
![PS_plot](https://github.com/quickcoffee/TDF-Starters-RUL/blob/master/plots/widget_plot.png?raw=true "Peter Sagan Predicted")
**Robert Hunter**
![RH_plot](https://github.com/quickcoffee/TDF-Starters-RUL/blob/master/plots/rh_plot.png?raw=true "Robert Hunter Predicted")

## Retired Riders Dashboard
Using the same scraper I also gathered career statistics on retired grand tour (cycling racs over 3 week such as Tour de France) starters and visualized the dataset via a [shiny dashboard](https://aarhus.shinyapps.io/RetiredGrandTourStarters/).
Please feel free and explore the data.
![Dashboard](https://github.com/quickcoffee/TDF-Starters-RUL/blob/master/plots/Dashboard.png?raw=true "GT Dashboard")

I hope you enjoy this project and let me know in case you have any questions or comments!
