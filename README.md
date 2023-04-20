# pierre-feux-ciseaux-
Jeux pierre deux ciseaux

def get_player_choice():
    """
    Demande au joueur de saisir son choix (pierre, feuille ou ciseaux)
    et renvoie le choix sous forme de chaîne de caractères.
    """
    valid_choices = ["pierre", "feuille", "ciseaux"]
    while True:
        player_choice = input("Choisissez pierre, feuille ou ciseaux : ").lower()
        if player_choice in valid_choices:
            return player_choice
        else:
            print("Choix invalide. Veuillez saisir pierre, feuille ou ciseaux.")

def get_computer_choice():
    """
    Génère un choix aléatoire pour l'ordinateur (pierre, feuille ou ciseaux)
    et renvoie le choix sous forme de chaîne de caractères.
    """
    choices = ["pierre", "feuille", "ciseaux"]
    return random.choice(choices)

def determine_winner(player_choice, computer_choice):
    """
    Compare le choix du joueur et celui de l'ordinateur pour déterminer le gagnant
    ou si c'est une égalité. Renvoie "player" si le joueur a gagné, "computer"
    si l'ordinateur a gagné, ou "tie" s'il y a égalité.
    """
    if player_choice == computer_choice:
        return "tie"
    elif player_choice == "pierre":
        if computer_choice == "ciseaux":
            return "player"
        else:
            return "computer"
    elif player_choice == "feuille":
        if computer_choice == "pierre":
            return "player"
        else:
            return "computer"
    elif player_choice == "ciseaux":
        if computer_choice == "feuille":
            return "player"
        else:
            return "computer"

def play_game():
    """
    Joue une partie complète de Pierre-Feuille-Ciseaux.
    """
    print("Bienvenue dans Pierre-Feuille-Ciseaux !")
    player_score = 0
    computer_score = 0
    while True:
        print(f"Score : joueur {player_score}, ordinateur {computer_score}")
        player_choice = get_player_choice()
        computer_choice = get_computer_choice()
        print(f"Le joueur a choisi {player_choice}. L'ordinateur a choisi {computer_choice}.")
        winner = determine_winner(player_choice, computer_choice)
        if winner == "player":
            print("Le joueur gagne cette manche !")
            player_score += 1
        elif winner == "computer":
            print("L'ordinateur gagne cette manche !")
            computer_score += 1
        else:
            print("Égalité !")
        if player_score == 3:
            print("Le joueur a gagné la partie !")
            break
        elif computer_score == 3:
            print("L'ordinateur a gagné la partie !")
            break

play_game()


Ce code utilise des fonctions pour simplifier le processus de jeu.
 La fonction get_player_choice demande au joueur de saisir son choix,
 la fonction get_computer_choice génère un choix aléatoire pour l'ordinateur, 
et la fonction determine_winner compare les choix du joueur et de l'ordinateur pour déterminer le gagnant
