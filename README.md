# FDS Project 25/26 del team "Copia di Copia di Untitled14"

### Code Index

0. **Imports + Mounting Drive**

1. **Read Dataset**
    - DataPath + Reading the data
    - Dataset split + Setting the seed

2. **Feature Engineering**
    - **Auxiliary functions**
        - A. `signal_features`: endgame_momentum
        - B. `status_penalty`: p1_avg_status, p2_avg_status, diff_avg_status
        - C. `hp_consinstency`: hp_consinstency
        - D. `switches`: p2_switches
        - E. `death`: estimated_death_diff, p1_survival_score, p2_survival_score
        - F. `stage_boosts`: p2_boost_sum, boost_diff
        - G. `revealed_fraction`: p2_revealed_frac, revealed_frac_diff
        - H. `ending_state_detailed`: p1_team_hp_avg, p2_team_hp_avg, team_hp_diff, p1_faint_count, faint_count_diff, p1_alive_count, p2_alive_count
    - **Applying Feature Engineering**
        - `def feature_engineering` function
        - `features_dict`
        - `feature_engineering` function call on train, validation & test
        - Selecting a subset of features for each model

3. **Train models**
    - KNN, XGBoost, SVM, Metamodel

4. **Evaluate models**
