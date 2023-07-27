# Unit-3-Assignment-1-Classes-and-Objects-

# game.py

class Player:
    def __init__(self, name):
        self.name = name
        self.score = 0

    def increase_score(self, points):
        self.score += points

class Game:
    def __init__(self):
        self.players = []

    def add_player(self, name):
        player = Player(name)
        self.players.append(player)

    def display_players(self):
        print("Players:")
        for player in self.players:
            print(f"{player.name} - Score: {player.score}")

    def play_round(self):
        for player in self.players:
            points = int(input(f"{player.name}, enter your points for this round: "))
            player.increase_score(points)

if __name__ == "__main__":
    game = Game()

    num_players = int(input("Enter the number of players: "))
    for i in range(num_players):
        name = input(f"Enter player {i+1} name: ")
        game.add_player(name)

    game.display_players()

    rounds = int(input("Enter the number of rounds to play: "))
    for i in range(rounds):
        print(f"Round {i+1}:")
        game.play_round()
        game.display_players()
