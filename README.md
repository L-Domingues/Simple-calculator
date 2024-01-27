# Simple-calculator

# importando tkinter
from tkinter import *
from tkinter import ttk

#cores
cor1 = '#232924' #balck
cor2 = '#f5f1ed'  #white
cor3 = '#1b214d' #blue
cor4 = '#bbbcc4' #gray
cor5 = '#eb7d00' #orange

#criar janela e configurações básicas
janela = Tk()
janela.title("Calculadora")
janela .geometry('240x308')
janela.config(bg=cor1)


#Dividir a janela em dois quadros e definir configurações
frame_screen = Frame(janela, width=240, height=50, bg=cor3)
frame_screen.grid(row=0, column=0)

frame_body = Frame(janela, width=240, height=270)
frame_body.grid(row=1, column=0)

#variavel todos valores
todosvalores = ''

#criando label
valortexto = StringVar()

#criando função
def entrada_valores(event):

    global todosvalores
    todosvalores = todosvalores+str(event)

    #passando valor para tela
    valortexto.set(todosvalores)

def calcular():
    global todosvalores
    resutado = eval(todosvalores)
    valortexto.set(str(resutado))
    todosvalores=str(resutado)

def limpartela():
    global todosvalores
    todosvalores = ''
    valortexto.set('')

app_label = Label(frame_screen, textvariable=valortexto, width=20,height=2,padx=7,relief=FLAT,anchor='e',justify=RIGHT, font=('Ivy 15'),bg=cor3,fg=cor2)
app_label.place(x=0,y=0)

#criar botões e os colocar no body
b_1 = Button(frame_body,command=limpartela,text='C', width=12,height=2, bg=cor4, font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_1.place(x=0, y=0)
b_2 = Button(frame_body,command=lambda: entrada_valores('%'),text='%', width=5,height=2,bg=cor4,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_2.place(x=120, y=0)
b_3 = Button(frame_body,command=lambda: entrada_valores('/'),text='/', width=5,height=2,bg=cor5,fg=cor2,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_3.place(x=180, y=0)

b_4 = Button(frame_body,command=lambda: entrada_valores('7'),text='7', width=5,height=2,bg=cor4,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_4.place(x=0, y=52)
b_5 = Button(frame_body,command=lambda: entrada_valores('8'),text='8', width=5,height=2,bg=cor4,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_5.place(x=60, y=52)
b_6 = Button(frame_body,command=lambda: entrada_valores('9'),text='9', width=5,height=2,bg=cor4,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_6.place(x=120, y=52)
b_7 = Button(frame_body,command=lambda: entrada_valores('*'),text='*', width=5,height=2,bg=cor5,fg=cor2,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_7.place(x=180, y=52)

b_8 = Button(frame_body,command=lambda: entrada_valores('4'),text='4', width=5,height=2,bg=cor4,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_8.place(x=0, y=103)
b_9 = Button(frame_body,command=lambda: entrada_valores('5'),text='5', width=5,height=2,bg=cor4,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_9.place(x=60, y=103)
b_10 = Button(frame_body,command=lambda: entrada_valores('6'),text='6', width=5,height=2,bg=cor4,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_10.place(x=120, y=103)
b_11 = Button(frame_body,command=lambda: entrada_valores('-'),text='-', width=5,height=2,bg=cor5,fg=cor2,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_11.place(x=180, y=103)

b_12 = Button(frame_body,command=lambda: entrada_valores('1'),text='1', width=5,height=2,bg=cor4,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_12.place(x=0, y=155)
b_13 = Button(frame_body,command=lambda: entrada_valores('2'),text='2', width=5,height=2,bg=cor4,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_13.place(x=60, y=155)
b_14 = Button(frame_body,command=lambda: entrada_valores('3'),text='3', width=5,height=2,bg=cor4,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_14.place(x=120, y=155)
b_15 = Button(frame_body,command=lambda: entrada_valores('+'),text='+', width=5,height=2,bg=cor5,fg=cor2,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_15.place(x=180, y=155)

b_16 = Button(frame_body,command=lambda: entrada_valores('0'),text='0', width=12,height=2, bg=cor4, font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_16.place(x=0, y=207)
b_17 = Button(frame_body,command=lambda: entrada_valores('.'),text='.', width=5,height=2,bg=cor4,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_17.place(x=120, y=207)
b_18 = Button(frame_body,command=calcular,text='=', width=5,height=2,bg=cor5,fg=cor2,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
b_18.place(x=180, y=207)


janela.mainloop()


