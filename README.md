import tkinter as tk

class BolaPisca:
    def __init__(self, root):
        self.root = root
        self.root.title("Bola que Pisca")
        self.canvas = tk.Canvas(root, width=200, height=200, bg="white")
        self.canvas.pack()
        self.bola = self.canvas.create_oval(50, 50, 150, 150, fill="red")
        self.visivel = True
        self.piscar()

    def piscar(self):
        if self.visivel:
            self.canvas.itemconfig(self.bola, state='hidden')
        else:
            self.canvas.itemconfig(self.bola, state='normal')
        self.visivel = not self.visivel
        self.root.after(500, self.piscar)  # pisca a cada 500 ms

if __name__ == "__main__":
    root = tk.Tk()
    bola = BolaPisca(root)
    root.mainloop()
