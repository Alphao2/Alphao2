import pygame
import sys

# Initialisierung
pygame.init()

# Fenstergröße
WINDOW_WIDTH = 800
WINDOW_HEIGHT = 600

# Farben
WHITE = (255, 255, 255)
BROWN = (139, 69, 19)
YELLOW = (255, 255, 0)

# Spielgeschwindigkeit
FPS = 60

# Spielergröße und Position
dino_width = 50
dino_height = 50
dino_x = 100
dino_y = WINDOW_HEIGHT - dino_height

# Kistengröße und Position
box_width = 50
box_height = 50
box_x = WINDOW_WIDTH
box_y = WINDOW_HEIGHT - box_height

# Geschwindigkeit des Dinosauriers und der Kisten
dino_speed = 5
box_speed = 5

# Erstelle das Fenster
window = pygame.display.set_mode((WINDOW_WIDTH, WINDOW_HEIGHT))
pygame.display.set_caption("Dinosaurier Spiel")

# Hauptschleife des Spiels
def main():
    clock = pygame.time.Clock()

    while True:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                pygame.quit()
                sys.exit()

        # Tastatureingabe
        keys = pygame.key.get_pressed()
        if keys[pygame.K_SPACE]:
            jump()

        # Bewege den Dinosaurier
        dino_x += dino_speed

        # Bewege die Kiste
        box_x -= box_speed

        # Überprüfe Kollision
        if check_collision(dino_x, dino_y, dino_width, dino_height, box_x, box_y, box_width, box_height):
            game_over()

        # Zeichne das Spiel
        draw_game(dino_x, dino_y, dino_width, dino_height, box_x, box_y, box_width, box_height)

        # Aktualisiere das Fenster
        pygame.display.update()

        clock.tick(FPS)

# Funktion für den Sprung des Dinosauriers
def jump():
    # Füge hier die Logik für den Dinosaurier-Sprung hinzu
    pass

# Funktion zur Überprüfung der Kollision
def check_collision(dino_x, dino_y, dino_width, dino_height, box_x, box_y, box_width, box_height):
    # Füge hier die Logik für die Kollisionsabfrage hinzu
    pass

# Funktion zum Anzeigen des Spiels
def draw_game(dino_x, dino_y, dino_width, dino_height, box_x, box_y, box_width, box_height):
    window.fill(WHITE)
    pygame.draw.rect(window, YELLOW, (dino_x, dino_y, dino_width, dino_height))
    pygame.draw.rect(window, BROWN, (box_x, box_y, box_width, box_height))

# Funktion für das Spielende
def game_over():
    # Füge hier die Logik für das Spielende hinzu
    pass

if __name__ == "__main__":
    main()
- 👋 Hi, I’m @Alphao2
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Alphao2/Alphao2 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
