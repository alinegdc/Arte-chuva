# painel criatvo_arte difital_Gif animado
#baixar a biblioteca 'GifAnimation' (https://github.com/extrapixel/gif-animation/tree/3.0)
#após baixar, extrair o arquivo, ir em Documents\Processing\libraries e adicionar a pasta extraída em libraries, no programa
#processign ir em sketch\ importar biblioteca\ GifAnimation


from __future__ import unicode_literals
add_library('GifAnimation')
from gif_helper import gif_export
"""
Uma grade de letras
"""
letras = "love♥"

"""
Alexandre B A Villares http://abav.lugaralgum.com - GPL v3 
Testing a helper for the Processing GifMaker Gif Animation librarie https://github.com/extrapixel/gif-animation/tree/3.0
Download from https://github.com/villares/processing-play/blob/master/export_GIF/unzip_and_move_to_libraries_GifAnimation.zip
This helper was inspired by an example by Art Simon https://github.com/APCSPrinciples/AnimatedGIF/
"""

def setup():
    size(600, 800)
    background(0)
    # Criar uma fonte PFont
    printArray(PFont.list())  # lista de fontes do computador
    f = createFont("GaroaHackerClubeBold.otf", 14)
    textFont(f)
    textAlign(CENTER, CENTER)
    textSize(26)
    frameRate(8)

def draw():
    background(0)
    passo = 30
    fill(255, 0, 0)
    # circle(150, 150, 150)
    textSize(200)
    colorMode(HSB)
    fill(frameCount % 256, 255, 255)
    text('☂', 150, 150)
    for y in range(24, height, passo):
        for x in range(12, width, passo):
            sorteio = int(random(len(letras)))
            letter = letras[sorteio]
            if (letter == '♥'):
                fill(255, 255, 255)
    textSize(300)
    colorMode(HSB)
    fill(frameCount % 100, 130, 255)
    text('☂', 450, 550)
    for y in range(24, height, passo):
        for x in range(12, width, passo):
            sorteio = int(random(len(letras)))
            letter = letras[sorteio]
            if (letter == '♥'):
                fill(255, 255, 255)
            else:
                fill(255)
            # Desenha a letra na tela
            #determinar a área da arte
            if (90 < x < 200 and 84 < y < 1000) or (
                  360 < x < 550 and 473 < y < 1000 ):
                pass
            else:
                textSize(26)
                text(letter, x, y)

    print(frameCount)
    gif_export(GifMaker, frames=50)
                
