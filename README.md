- 👋 Hi, I’m @Arshan001
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Arshan001/Arshan001 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import pygame
import sys

# Initialize Pygame
pygame.init()

# Constants
WIDTH, HEIGHT = 800, 600
FPS = 60

# Colors
WHITE = (255, 255, 255)

# Initialize game window
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Simple Racing Game")
clock = pygame.time.Clock()

# Car
car_image = pygame.Surface((50, 30))
car_image.fill((255, 0, 0))
car_rect = car_image.get_rect()
car_rect.center = (WIDTH // 2, HEIGHT - 50)

# Game loop
while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT] and car_rect.left > 0:
        car_rect.x -= 5
    if keys[pygame.K_RIGHT] and car_rect.right < WIDTH:
        car_rect.x += 5

    # Update game elements

    # Draw background
    screen.fill(WHITE)

    # Draw car
    screen.blit(car_image, car_rect)

    # Update display
    pygame.display.flip()

    # Cap the frame rate
    clock.tick(FPS)
