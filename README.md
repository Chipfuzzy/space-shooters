import pgzrun
import random

WIDTH = 1200
HEIGHT = 600

WHITE = (255,255,255)
BLUE = (0,0,255)

ship = Actor('correct rocket')
UFO = Actor('correct spaceship')

ship.pos = (WIDTH//2, HEIGHT-60)

speed = 5

bullets = []

enemies = []

for x in range(8):
    for y in range(4):
        enemies .append(Actor('correct spaceship'))
        enemies[-1].x = 100 +50*x
        enemies[-1].y = 80 + 50*y

score = 0
direction = 1
ship.dead = False
ship.countdown = 90

def displayScore():
    screen.draw.text(str(score),(50,30))

def gameOver():
    screen.draw.text("GAME OVER", (250,100))

def on_key_down(key):
    if ship.dead == False
    if key == keys.SPACE:
        bullets.append(Actor('correct bullet'))
        bullets[-1].x = ship.x
        bullets[-1].y = ship.y - 50

def update():
    global score
    global direction
    moveDown = False

    if ship.dead == False:
        if keyboard.left:
            ship.x -= speed
            if ship.x <= 0:
                ship.x = 0

        elif keyboard.right:
            ship.x += speed
            if ship.x >= WIDTH:
                ship.x = WIDTH

    for bullet in bullets:
        if bullet.y <=0 :
            bullets.remove(bullet)
        else:
            bullet.y -= 10
