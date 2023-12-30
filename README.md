# DIGIBHEM
import pygame
import os

# Initialize Pygame
pygame.init()

# Set the path to your music file
file_path = "C:\\Users\\Hp\Downloads\\[iSongs.info] 02 - Salaar Cease Fire Telugu Trailer Theme.mp3"
# Set up̥ the display (you can adjust the size as needed)
pygame.display.set_mode((200, 200)) 

# Load the music file
pygame.mixer.music.load(file_path) 

# Functions for music control
def play_music():
    pygame.mixer.music.play()

def pause_music():
    pygame.mixer.music.pause()

def stop_music():
    pygame.mixer.music.stop()

# Main loop
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.KEYDOWN:
            if event.key == pygame.K_ESCAPE:
                running = False
            elif event.key == pygame.K_SPACE:
                if pygame.mixer.music.get_busy():
                    pause_music()
                else:
                    play_music()
            elif event.key == pygame.K_s:
                stop_music()

        elif event.type == pygame.QUIT:
            running = False

    pygame.display.flip()

    # Add a small delay to avoid consuming too much CPU
    pygame.time.delay(10)

# Quit Pygame
pygame.quit()
