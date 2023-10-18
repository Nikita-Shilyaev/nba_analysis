# nba_analysis
### Goal:
To find out if there is a statistically significant effect of a player's height and age on whether he will be selected in the NBA draft, the round in which he will be selected, and the draft number at which he will be selected.

### Data: 
Publicly posted data on kaggle.com with statistics and demographic information of former and current NBA players.

### Results: 
1) no significant relationship was found between player height and the outcome of being selected/not selected in the draft:
- biserial correlation coefficient between the 'drafted_flag' variable taking the values '1' - was selected in the draft and '0' - was not selected, and the continuous player height variable 'player_age': r = 0.153 at pvalue = 1.35e-14;
  
2) little to no correlation was found between player height and the round in which the player was selected:
- biserial correlation coefficient between 'draft_round' taking values '1' - round 1 and '0' - round 2, and 'player_height' r = 0.061 at pvalue = 0.024;
  
3) 
