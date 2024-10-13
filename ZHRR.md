code = 1
codepart = 1
round = 1
old_map = 0
your_round = 0
game = 1
total_round = 0
highest_rounds = 0
total_maps = 0
maplist = ["Terra Maledicta (Vanguard Zombies)", "Der Anfang (Vanguard Zombies)", "The Archon (Vanguard Zombies)", "Bus Depot (Bo2 Zombies)", "Die Rise (Bo2 Zombies)", "Nacht Der Untoten (WaW Zombies)", "Farm (Bo2 Zombies)", "Shi No Numa (World at War)", "Kino Der Toten (Bo1 Zombies)", "Alpha Omega (Bo4 Zombies)", "Voyage of Despair (Bo4 Zombies)", "Shangri-La (Bo1 Zombies)", "Blood of the Dead (Bo4 Zombies)", "TranZit (Bo2 Zombies)", "Outbreak (Cold War Zombies)", "Firebase Z (Cold War Zombies)", "Forsaken (Cold War Zombies)", "Shi No Numa (Vanguard Zombies)", "Der Riese (WaW Zombies)", "The Giant (Bo3 Zombies)", "Five (Bo1 Zombies)", "IX (Bo4 Zombies)", "Tag Der Toten (Bo4 Zombies)", "Nuketown (Bo2 Zombies)", "Ascension (Bo1 Zombies)", "Classified (Bo4 Zombies)", "Verruckt (Bo1 Zombies)", "Die Maschine (Cold War Zombies)", "Mauer Der Toten (Cold War Zombies)", "Moon (Bo3 Zombies Chronicles)", "Buried (Bo2 Zombies)", "Revelations (Bo3 Zombies)", "Zetsubou No Shima (Bo3 Zombies)", "Ancient Evil (Bo4 Zombies)", "Call of the Dead (Bo1 Zombies)", "Gorod Krovi (Bo3 Zombies)", "Town (Bo2 Zombies)", "Dead of the Night (Bo4 Zombies)", "Mob of the Dead (Bo2 Zombies)", "Shadows of Evil (Bo3 Zombies)", "Origins (Bo2 Zombies)", "Der Eisendrache (Bo3 Zombies)"]

print("ZHRR")
print("Tutorial:\ntype Tutorial to start Tutorial\ntype skip to skip Tutorial")

while code == 1:
    text = input()
    if codepart == 1:
        if text == "Tutorial":
            codepart = 2
            print("Type start to start the game.\nOnce you start the game you will get a random Call of duty Zombies map.\nWrite the round that you got on the Zombies map.\nThe goal is to get a higher round than the last Zombies map.\nType 0 to change the Zombies map if you don't have the map.")
            text = 0
        elif text == "skip":
            codepart = 2
            text = 0
    if codepart == 2:
        print("\n")
        if text == "start":
             game = 1
             while game == 1:
                 import random
                 map = random.randint(0, 41)
                 while old_map == map:
                     map = random.randint(0, 41)
                 old_map = map
             
                 print(f"At least round: {round} on the Zombies map: {maplist[map]}")
                 your_round = int(input("Round: "))
                 total_round = total_round + your_round
                 rf = round - 1
                 if your_round == 0:
                     print("change map\n")
                 else:
                     highest_rounds = rf
                     total_maps = total_maps + 1
                     round = your_round + 1
                     print("\n")
                     if rf > your_round:
                         print(f"Maps Played: {total_maps} Total Rounds Played: {total_round} Highest Rounds: {highest_rounds} ")
                         round = 1
                         total_round = 0
                         print("\n")
                         game = 0
                         print("\n")
