import pygame
import sys

try:
    pygame.init()
    
    WIDTH = 800
    HEIGHT = 600
    
    screen = pygame.display.set_mode((WIDTH, HEIGHT))
    pygame.display.set_caption("Finite Dungeons")
    
    clock = pygame.time.Clock()
    
    running = True
    
    while running:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                break
    
        screen.fill((30, 30, 30))
    
        pygame.display.update()
    
        clock.tick(60)
finally:
    pygame.quit()
    sys.exit()
