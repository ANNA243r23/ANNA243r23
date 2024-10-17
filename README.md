class Player:
    def __init__(self, name):
        self.name = name
        self.is_running = False
        self.is_sprinting = False
        self.is_jumping = False
        self.is_climbing = False
        self.energy = 100  # Spieler hat 100% Energie
    
    def walk(self):
        if not self.is_running and not self.is_sprinting:
            print(f"{self.name} is walking.")
        else:
            print(f"{self.name} can't walk while running or sprinting.")
    
    def run(self):
        if self.energy >= 10:
            self.is_running = True
            self.energy -= 10
            print(f"{self.name} is running. Energy left: {self.energy}%")
        else:
            print(f"{self.name} is too tired to run.")
    
    def sprint(self):
        if self.energy >= 20:
            self.is_sprinting = True
            self.energy -= 20
            print(f"{self.name} is sprinting fast! Energy left: {self.energy}%")
        else:
            print(f"{self.name} is too tired to sprint.")
    
    def jump(self):
        if not self.is_jumping:
            self.is_jumping = True
            print(f"{self.name} is jumping!")
            self.is_jumping = False  # After jumping, the player is back on the ground
    
    def climb(self):
        if self.energy >= 15:
            self.is_climbing = True
            self.energy -= 15
            print(f"{self.name} is climbing a wall. Energy left: {self.energy}%")
        else:
            print(f"{self.name} is too tired to climb.")
    
    def stop(self):
        self.is_running = False
        self.is_sprinting = False
        print(f"{self.name} has stopped.")

# Beispielnutzung:
player = Player("Alex")

player.walk()
player.run()
player.jump()
player.sprint()
player.climb()
player.stop()
