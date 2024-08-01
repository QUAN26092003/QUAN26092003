.import pygame
import sys

# Khởi tạo Pygame
pygame.init()

# Kích thước của cửa sổ
width, height = 800, 600
window = pygame.display.set_mode((width, height))

# Màu sắc
blue = (0, 0, 255)

# Tọa độ và kích thước của hình vuông
x, y = width // 2, height // 2
size = 50
speed = 5

# Vòng lặp chính của trò chơi
while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT]:
        x -= speed
    if keys[pygame.K_RIGHT]:
        x += speed
    if keys[pygame.K_UP]:
        y -= speed
    if keys[pygame.K_DOWN]:
        y += speed

    # Làm mới màn hình
    window.fill((0, 0, 0))
    pygame.draw.rect(window, blue, (x, y, size, size))
    pygame.display.flip()
    
    pygame.time.delay(30)

--->
