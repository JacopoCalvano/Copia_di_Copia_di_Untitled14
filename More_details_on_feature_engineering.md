# MORE DETAILS ON FEATURE ENGNINEERING

This file contains a brief description of the functions used for feature engineering (Section 2.I of the notebook)


## A. signal_features — `endgame_momentum`

**Core Idea:**  
This feature captures how the HP advantage evolves in the final phase of the battle.  
We track the HP percentage of both active Pokémon across turns and compute the HP difference (`p1_hp - p2_hp`).  
A positive value indicates increasing advantage for Player 1; a negative value indicates the opposite.

---

## B. status_penalty — `p1_avg_status`, `p2_avg_status`, `diff_avg_status`

**Core Idea:**  
This feature quantifies how much each player is penalized by negative status conditions throughout the battle.  
Each status (sleep, burn, paralysis, poison, etc.) is mapped to a numerical penalty reflecting its impact on performance.  
We average these penalties.

---

## C. hp_consinstency — `hp_consinstency`

**Core Idea:**  
This feature measures how stable Player 1’s HP trend is during the battle:  
`hp_consinstency = 1 - std(hp_pct)`.  

---

## D. switches — `p2_switches`

**Core Idea:**  
This feature counts how many times Player 2 switches their active Pokémon.  
Frequent switching can reflect strategic adaptation or being forced into unfavorable positions. See e.g. [“Applying Game Theory to Pokémon”](https://www.smogon.com/forums/threads/applying-game-theory-to-pokemon-tl-dr.21646/) for further discussion.  

---

## E. death — `estimated_death_diff`, `p1_survival_score`, `p2_survival_score`

**Core Idea:**  
This feature group summarizes how many Pokémon each player has effectively “lost.”  
We count officially fainted Pokémon, but also add fractional deaths for Pokémon ending the battle at very low HP. 
This yields an *estimated death count* per player. 

---

## F. stage_boosts — `p2_boost_sum`, `boost_diff`

**Core Idea:**  
This feature family measures the cumulative positive stat boosts obtained during the match.  
For every turn, we compute the increments in stat stages relative to the previous turn and accumulate only the *positive* changes.  

---

## G. revealed_fraction — `p2_revealed_frac`, `revealed_frac_diff`

**Core Idea:**  
This block measures how much of each player's team has been revealed during the game.
A lower revealed fraction is beneficial because revealing fewer Pokémon preserves strategic uncertainty.See e.g ["Guide to switches"](https://www.vgcguide.com/switching).

---

## H. ending_state_detailed — `p1_team_hp_avg`, `p2_team_hp_avg`, `team_hp_diff`, `p1_faint_count`, `faint_count_diff`, `p1_alive_count`, `p2_alive_count`

**Core Idea:**  
This feature block captures a detailed snapshot of both teams at the end of the match.  
These metrics collectively represent how dominant or balanced the final board state is.

---
