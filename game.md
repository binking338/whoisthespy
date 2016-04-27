# who is the spy？

## game action

### create
create() : game_handle;

### join
join(game_handle, player_name) : player_handle;

### players
players(game_handle, player_handle) : palyer_names

### ready
ready(game_handle, host_handle) : code_ready;
> code_ready
> * success
> * not_host
> * not_enough_player
> * unknown_failure

### destroy
destroy(game_handle, host_handle) : code_destroy;

### new
new(game_handle, host_handle) : code_new;
> code_new
> * success
> * not_host
> * unknown_failure

### pick
pick(game_handle, player_handle) : string;

### vote
vote(game_handle, player_handle, spy_name) : code_vote;
> code_vote
> * success
> * not_in_round
> * not_player
> * spy_not_player
> * voted
> * unknown_failure

### judge
judge(game_handle) : code_judge;
> code_judge
> * continue
> * civilian_win
> * spy_win

## model

### game

* game_handle : int

* status : int

    * recruit
    * ready
    * destroied

* players : [player]

* current_round : round

### player

* name : string

* handle : int

### round

* spy_word : string

* civilian_word : string

* is_over : bool

* spys : [int]

* alives : [int]

* deads : [int]

* vote_history : [[[player_handle,spy_handle]]]

* votes : [[player_handle,spy_handle]]