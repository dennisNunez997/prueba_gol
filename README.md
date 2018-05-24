# prueba_gol
prueba2 Dennis Allexisn Nuñez JImenez

#prueba_gol

#utilizacion de la libreria Tkinter
from tkinter import *
#bpy es una libreria que permitira obtener la localizacion del objeto
import bpy
tk = Tk()
#creacion de de la ventana con sus respectivas dimensiones
canvas = Canvas(tk, width=535, height = 500)
canvas.pack()

#llamado e iplementacion de imagenes

#implementacion de la imagen del arco
my_image1 = PhotoImage(file ="arco.png")
canvas.create_image(0,0, anchor=NW, image= my_image1)
#implementacion de la imagen balon
my_image2 = PhotoImage(file = "balon.png")
canvas.create_image(400,50, anchor = NW, image = my_image2)
#implementacion de la imagen palabra "GOL""
my_image3 = PhotoImage(file = "palabra.png")
canvas.create_image(200,200, anchor = NW, image = my_image3)
#CREACION DE EVENTOS PARA BALON"
def image2(event):
    #mientras la posicion de balon sea a la izquierda
    if event.keysym == 'Left':
        canvas.move(2,-3,0)
    #mientras la posicion del balon sea hacia la derecha
    elif event.keysym == 'Right':
        canvas.move(2,3,0)    

#se llama a las teclas que se moveran de izquirda a derecha con respecto al balon
canvas.bind_all('<KeyPress-Left>',image2)
canvas.bind_all('<KeyPress-Right>',image2)
#se imprime la ubicacion del objeto usando la libreria bpy
print(bpy.data.object[image2].location)
tk.mainloop()

