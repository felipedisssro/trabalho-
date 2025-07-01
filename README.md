import tkinter as tk
from tkinter import messagebox

def calcular_media():
    
     entrada_nome.get()
        exercicios = float(entrada_exercicios.get())
        d1 = float(entrada_d1.get())
        d2 = float(entrada_d2.get())
        d3 = float(entrada_d3.get())
        f1 = float(entrada_f1.get())
        f2 = float(entrada_f2.get())
        f3 = float(entrada_f3.get())

        media_desafios = (d1 + d2 + d3) / 3
        media_projeto = (f1 + f2 + f3) / 3
        media_final = (exercicios + media_desafios + media_projeto * 2) / 4

        if media_final >= 6:
            mensagem = f"Parabéns! Você foi aprovado com nota {media_final:.}"
        if media_final >= 4:
            mensagem = f"Você ainda não foi aprovado! Sua nota foi {media_final:.}. Você terá a opção de fazer o IFA!!!"
        else:
            mensagem = f"Com a nota {media_final:} você não foi aprovado! Veja pelo lado bom, você irá cursar a disciplina novamente semestre que vem!!!"

        messagebox.showinfo("Resultado", mensagem)



janela = tk.Tk()
janela.title("---Média---")
janela.geometry("400x200")

tk.Label(janela, text="nome:").pack()
entrada_nome = tk.Entry(janela); entrada_nome.pack()

tk.Label(janela, text="média dos Exercícios:").pack()
entrada_exercicios = tk.Entry(janela); entrada_exercicios.pack()

tk.Label(janela, text="Nota Desafio 1:").pack()
entrada_d1 = tk.Entry(janela); entrada_d1.pack()

tk.Label(janela, text="Nota Desafio 2:").pack()
entrada_d2 = tk.Entry(janela); entrada_d2.pack()

tk.Label(janela, text="Nota Desafio 3:").pack()
entrada_d3 = tk.Entry(janela); entrada_d3.pack()

tk.Label(janela, text="Nota Projeto - Fase 1:").pack()
entrada_f1 = tk.Entry(janela); entrada_f1.pack()

tk.Label(janela, text="Nota Projeto - Fase 2:").pack()
entrada_f2 = tk.Entry(janela); entrada_f2.pack()

tk.Label(janela, text="Nota Projeto - Fase 3:").pack()
entrada_f3 = tk.Entry(janela); entrada_f3.pack()

tk.Button(janela, text="Calcular Média", command=calcular_media, bg="lightblue").pack(pady=10)

janela.mainloop()
