# A Simple [Battlesnake](http://play.battlesnake.com) Written in Python

## Vicky's Logic
1. 
```
FOOD_SEARCH_THRESHOLD = max(50, 95 - len(snake_body))
if len(snake_body) < 4 or health < FOOD_SEARCH_THRESHOLD or not is_longest():
    get_food()
chase_tail()
```

2. Eat food
```
def get_food():
    target_food_path = find_food_path()
    return move_direction(head, target_food_path[1])

# return the path to food
def find_food_path(board):
	sort food by distance from our head to food increasingly
    best_food_path = find_best_food_path()
    return best_food_path

# check future of us getting each food, and find longest safe path in radius = our length
# longest safe path is a path containing empty cells
# ideally, longest safe path should equal our length + 1
# return the path to the best food
```

TODO:
if there are more than 2 snakes, we need to make ourself long enough
```
if snakes > 2:
	if is_second_longest():
		kill_others()
	else:
		get_food()
else:
	if not is_longest():
		get_food()
	else:
		kill_others()
```

## Irene's Logic
1. use heuristic to get the senario that has the highest score, then make a move <br>
TODO:
    * how to give weights to snakes? food?
	* when health is low, increase the weight of food
	* what is the low health threshold?