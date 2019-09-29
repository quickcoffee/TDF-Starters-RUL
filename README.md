# TDF Starters Remaining-Useful-Life (RUL)

## Intro
This little project uses a neural network with LSTM-cells to predict the career end of Tour de France starters.  
To train the network, data about Tour de France starters between 1995 to 2019 from the excellent ressource https://www.procyclingstats.com has been scrapped. The scrapped data was then brought into the long-format and some features such as a cumulative count of years riding for a WorldTour/ProContinental/Continental-Team have been added. This data was then feed into a rather simple neural network with two layers of LSTM cells and a dense output layer with one cell and a linear activation function. The final model resulted in a RMSE of 2.426 and R2 of 0.742.
The data can be found on Kaggle: https://www.kaggle.com/lukassteger/career-statistics-tdf-starters-19952019
The model therefore gives a rough estimate on when a rider will end his career, but should also be seen in the light of the project's weaknesses: Data quality could be enhanced, as riders with breaks in their careers such as doping-bans or being with out a contract are included in the dataset. Also features such as height or weight, were not included due to missing data. Further, the integration of non-time varying variables could be done via a multi-input network architecture. The network's hyperparameters and the number of features could be enhanced in the future, in order to obtain better results.
Inspirations for this project were taken from RUL-projects such as https://github.com/gm-spacagna/deep-ttf/ and https://github.com/LahiruJayasinghe/RUL-Net
Another way to approach is project is to take it as a classification problem (eg. Is rider XY still active in 5 years? Yes/No) rather than a regression problem.
Unfortunately does Github not support the ipywidgets and in order to interactively explore the model's results it need to be opened as a Jupyter notebook.

##Results

