# Dataset Description

## Summary of data

Here, you'll find a summary of each data set in the **2026 Big Data Bowl**, a list of key variables to join on, and a description of each variable. The tracking data is provided by the **NFL Next Gen Stats** team.

## External Data

The 2026 Big Data Bowl allows participants to use external NFL data as long as it is **free** and **publicly available** to all participants. Examples of sources that could be used include **nflverse** and **Pro Football Reference**.

**Note:** The `gameId` and `playId` of the Big Data Bowl data merge with the `old_game_id` and `play_id` of nflverse's play-by-play data.

---

## Files

### `train/`

#### `input_2023_w[01-18].csv`

The input data contains tracking data **before the pass is thrown**.

- `game_id`: Game identifier, unique (numeric)
- `play_id`: Play identifier, not unique across games (numeric)
- `player_to_predict`: whether or not the x/y prediction for this player will be included in the corresponding output file (bool)
- `nfl_id`: Player identification number, unique across players (numeric)
- `frame_id`: Frame identifier for each play/type, starting at 1 for each `game_id`/`play_id`/file type (input or output) (numeric)
- `play_direction`: Direction that the offense is moving (left or right)
- `absolute_yardline_number`: Distance from end zone for possession team (numeric)
- `player_height`: player height (ft-in)
- `player_name`: player name (text)
- `player_weight`: player weight (lbs)
- `player_birth_date`: birth date (yyyy-mm-dd)
- `player_position`: the player's position (the specific role on the field that they typically play)
- `player_side`: team player is on (Offense or Defense)
- `player_role`: role player has on play (Defensive Coverage, Targeted Receiver, Passer or Other Route Runner)
- `x`: Player position along the long axis of the field, generally within 0 - 120 yards. (numeric)
- `y`: Player position along the short axis of the field, generally within 0 - 53.3 yards. (numeric)
- `s`: Speed in yards/second (numeric)
- `a`: Acceleration in yards/second^2 (numeric)
- `o`: orientation of player (deg)
- `dir`: angle of player motion (deg)
- `num_frames_output`: Number of frames to predict in output data for the given `game_id`/`play_id`/`nfl_id`. (numeric)
- `ball_land_x`: Ball landing position along the long axis of the field, generally within 0 - 120 yards. (numeric)
- `ball_land_y`: Ball landing position along the short axis of the field, generally within 0 - 53.3 yards. (numeric)

---

#### `output_2023_w[01-18].csv`

The output data contains tracking data **after the pass is thrown**.

- `game_id`: Game identifier, unique (numeric)
- `play_id`: Play identifier, not unique across games (numeric)
- `nfl_id`: Player identification number, unique across players. (numeric)
- `frame_id`: Frame identifier for each play/type, starting at 1 for each `game_id`/`play_id`/file type (input or output). The maximum value for a given `game_id`, `play_id` and `nfl_id` will be the same as the `num_frames_output` value from the corresponding input file. (numeric)
- `x`: Player position along the long axis of the field, generally within 0 - 120 yards. (numeric)
- `y`: Player position along the short axis of the field, generally within 0 - 53.3 yards. (numeric)

---

## Supplementary

Contextual info about the game/play.

- `game_id`: Game identifier, unique (numeric)
- `season`: Season of game
- `week`: Week of game
- `game_date`: Game Date (time, mm/dd/yyyy)
- `game_time_eastern`: Start time of game (time, HH:MM:SS, EST)
- `home_team_abbr`: Home team three-letter code (text)
- `visitor_team_abbr`: Visiting team three-letter code (text)
- `home_final_score`: The total amount of points scored by the home team in the game (numeric)
- `visitor_final_score`: The total amount of points scored by the visiting team in the game (numeric)
- `play_id`: Play identifier, not unique across games (numeric)
- `play_description`: Description of play (text)
- `quarter`: Game quarter (numeric)
- `game_clock`: Time on clock of play (MM:SS)
- `down`: Down (numeric)
- `yards_to_go`: Distance needed for a first down (numeric)
- `possession_team`: Team abbr of team on offense with possession of ball (text)
- `defensive_team`: Team abbr of team on defense (text)
- `yardline_side`: 3-letter team code corresponding to line-of-scrimmage (text)
- `yardline_number`: Yard line at line-of-scrimmage (numeric)
- `pre_snap_home_score`: Home score prior to the play (numeric)
- `pre_snap_visitor_score`: Visiting team score prior to the play (numeric)
- `pass_result`: Dropback outcome of the play (C: Complete pass, I: Incomplete pass, S: Quarterback sack, IN: Intercepted pass, R: Scramble, text)
- `play_nullified_by_penalty`: Whether or not an accepted penalty on the play cancels the play outcome. Y stands for yes and N stands for no. (text)
- `pass_length`: The distance beyond the LOS that the ball traveled not including yards into the endzone. If thrown behind LOS, the value is negative. (numeric)
- `offense_formation`: Formation used by possession team (text)
- `receiver_alignment`: Enumerated as 0x0, 1x0, 1x1, 2x0, 2x1, 2x2, 3x0, 3x1, 3x2 (text)
- `route_of_targeted_receiver`: Route ran by targeted receiver (text)
- `play_action`: Indicates if there was play action on the play (binary)
- `dropback_type`: The type of drop back after the snap by the QB (Traditional, Designed Rollout, Scramble, Scramble Rollout, Designed Rollout Left, Designed Rollout Right, Scramble Rollout Left, Scramble Rollout Right, Designed Run, QB Draw, Rollout, text)
- `dropback_distance`: The distance the QB dropped back (yards) behind the center after the snap (numeric)
- `pass_location_type`: The location type of where the QB was at the time of throw - InsideTackle Box, Outside Left, Outside Right or Unknown (text)
- `defenders_in_the_box`: Number of defenders in close proximity to line-of-scrimmage (numeric)
- `team_coverage_man_zone`: Indicates the overarching type of coverage (Man/Zone) on a play (text)
- `team_coverage_type`: The specific kind of coverage assigned on the play (text)
- `penalty_yards`: yards gained by offense by penalty (numeric)
- `pre_penalty_yards_gained`: Net yards gained by the offense, before penalty yardage (numeric)
- `yards_gained`: Net yards gained by the offense, including penalty yardage (numeric)
- `expected_points`: Expected points on this play (numeric)
- `expected_points_added`: Delta of expected points on this play (numeric)
- `pre_snap_home_team_win_probability`: The win probability of the home team before the play (numeric)
- `pre_snap_visitor_team_win_probability`: The win probability of the visiting team before the play (numeric)
- `home_team_win_probability_added`: Win probability delta for home team (numeric)
- `visitor_team_win_probility_added`: Win probability delta for visitor team (numeric)