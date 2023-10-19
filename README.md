# nba_analysis
### Goal:
To find out if there is a statistically significant effect of a player's height and age on whether he will be selected in the NBA draft, the round in which he will be selected, and the draft number at which he will be selected.

### Data: 
Publicly posted data on kaggle.com with statistics and demographic information of former and current NBA players.

### Results: 
1) no significant relationship was found between player height and the outcome of being selected/not selected in the draft:
- biserial correlation coefficient between the *'drafted_flag'* variable taking the values '1' - was selected in the draft and '0' - was not selected, and the continuous player height variable *'player_age'*: r = 0.153, pvalue = 1.35e-14;
  
2) little to no correlation was found between player height and the round in which the player was selected:
- biserial correlation coefficient between *'draft_round'* taking values '1' - round 1 and '0' - round 2, and *'player_height'*: r = 0.061, pvalue = 0.024;
  
3) Pearson's correlation coefficient between the variable 'draft_number', taking values between 1 and 60 inclusive, and 'player_height' was: r = -0.09. Which also indicates almost zero influence of height on draft number.

4) between the same variables, but now with player age, the correlation is more pronounced:
- being selected/not selected in the draft: r = -0.368, pvalue=4.05e-76;
- being selected in the draft in round 1/2: r = -0.36, pvalue=1.21e-43;
- the dependence of draft number on age: r = 0.416.
The resulting coefficients show that there is a dependence (though not strong) on all three variables, and it is in favor of younger players.

**I decided to check how strong this dependence is using the logistic regression model.**

5) two predictors *'age'* and *'player_height'* participated in the model and were centered around their mean values.
   
- The intercept coefficient = 0.895, thus np.exp(0.895) = 2.45 - a player of average height and age relative to other players in the draft has a nearly 2.5 times higher chance of being selected.
  
- The coefficient on the predictor *'age'* = -0.378, and np.exp(-0.378) = 0.685. This means that if a player's age increases by 1 year, his chance of being selected decreases by 31%.
  
- The coefficient on the predictor *'player_height'* is expectedly very low = 0.038, and np.exp(0.038) = 1.039: player height has almost no effect on the chance of being selected.

### Conclusion:
Judging from the data obtained from the calculations performed, we can say that height has almost no effect on whether a player will be selected or not. Age has a noticeable impact on draft picks, and it can be concluded that teams are more likely to select a younger player, which makes sense. However, with only age and height as inputs, we cannot conclude that, of two players with the same height but different ages, the younger one will be selected. Because it is unlikely that the team management takes only these two parameters into account. Professionals will focus on such things as college and high school game statistics, ratings of professional publications, player's health, as well as such difficult to measure indicators as basketball intelligence of an athlete, his psychological and social features. Perhaps coupled with the metrics described above, age and height will have a different share of influence on a player's draft selection.
