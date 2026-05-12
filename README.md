# Is_303_proj3

#Move Class - Monet
#Move Object - Katie
#Pokemon Class - Miles
#Pokemon Object - Owen




import random


# Move class, this represents an attack or ability a Pokemon can use
class Move:
    def __init__(self, move_name, elemental_type, low_attack_points, high_attack_points):
        # store the move's name, type, and damage range
        self.move_name = move_name
        self.elemental_type = elemental_type
        self.low_attack_points = low_attack_points
        self.high_attack_points = high_attack_points

    def get_info(self):
        # return a formatted string with all the move's details
        return f"{self.move_name} (Type: {self.elemental_type}): {self.low_attack_points} to {self.high_attack_points} Attack Points"

    def generate_attack_value(self):
        # randomly pick a damage value within the move's range
        return random.randint(self.low_attack_points, self.high_attack_points)

# Move objects to test the class and generate some attack values

tackle = Move("Tackle", "Normal", 5, 20)
quick_attack = Move("Quick Attack", "Normal", 6, 25)
slash = Move("Slash", "Normal", 10, 30)
flamethrower = Move("Flamethrower", "Fire", 5, 30)
ember = Move("Ember", "Fire", 10, 20)
water_gun = Move("Water Gun", "Water", 5, 15)
hydro_pump = Move("Hydro Pump", "Water", 20, 25)
vine_whip = Move("Vine Whip", "Grass", 10, 25)
solar_beam = Move("Solar Beam", "Grass", 18, 27)

# put all moves in a list
move_list = [tackle, quick_attack, slash, flamethrower, ember, water_gun, hydro_pump, vine_whip, solar_beam]

# randomly pick 3 moves with no repeats, print their info and a generated attack value
for i in range(3):
    chosen_move = random.choice(move_list)
    print(chosen_move.get_info())
    print("Generated attack value: ", chosen_move.generate_attack_value())
    move_list.remove(chosen_move)





# Pokemon Class

class Pokemon:
    def __init__(self, name, elemental_type, hit_points):
        self.name = name
        self.elemental_type = elemental_type
        self.hp = hit_points

    def get_info(self):
        return f"{self.name} - (Type: {self.elemental_type} - HP: {self.hit_points})"
    
    def heal(self):
        self.hit_points += 15
        print(f"{self.name} has been healed to {self.hit_points} hit points.")


# Pokemon objects

#Creates the 3 Pokemon as objects
bulbasaur = Pokemon("Bulbasaur", "Grass", 60)
charmander = Pokemon("Charmander", "Fire", 55)
squirtle = Pokemon("Squirtle", "Water", 65)

#Call get_info method for Charmander and print result
print(charmander.get_info())

#Call heal method for Charmander

charmander.heal()
print(charmander.get_info())

#Hit points should have increased for Charmander

#Put the Pokemon in a list
pokemon_list = [bulbasaur, charmander, squirtle]

#Loop through the list to print the info for each Pokemon
print("Pokemon Info")
for pokemon in pokemon_list:
    print(pokemon.get_info())

