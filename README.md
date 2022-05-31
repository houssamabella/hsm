import tkinter as tk
from tkinter import ttk

LARGEFONT = ("Verdana", 150)


class tkinterApp(tk.Tk):

	# __init__ function for class tkinterApp
	def __init__(self, *args, **kwargs):
		# __init__ function for class Tk
		tk.Tk.__init__(self, *args, **kwargs)

		# creating a container
		container = tk.Frame(self)
		container.pack(side="top", fill="both", expand=True)

		container.grid_rowconfigure(0, weight=1)
		container.grid_columnconfigure(0, weight=1)

		# initializing frames to an empty array
		self.frames = {}

		for F in (Start_Page, Page1, Page2):
			frame = F(container, self)

			# initializing frame of that object from
			# start_page, page1, page2 respectively with
			# for loop
			self.frames[F] = frame

			frame.grid(row=0, column=0, sticky="nsew")

		self.show_frame(Start_Page)

	def show_frame(self, cont):
		frame = self.frames[cont]
		frame.tkraise()


# first window frame start_page

class Start_Page(tk.Frame):
	def __init__(self, parent, controller):
		tk.Frame.__init__(self, parent)

		label = ttk.Label(self, text="BIENVENU SUR LES MODELES STCHOCASTIQUE", font=('LARGEFONT', 40))

		label.grid(row=0, column=4, padx=10, pady=10)

		button1 = ttk.Button(self, text="BLACK AND SCHOLES", command=lambda: controller.show_frame(Page1))

		# putting the button in its place by
		# using grid
		button1.grid(row=1, column=5, padx=10, pady=10)

		# button to show frame 2 with text layout2
		button2 = ttk.Button(self, text="MERTON ", command=lambda: controller.show_frame(Page2))

		# putting the button in its place by
		# using grid
		button2.grid(row=2, column=5, padx=10, pady=10)

		button3 = ttk.Button(self, text="HESTON", command=lambda: controller.show_frame(Page3))
		button3.grid(row=3, column=5, padx=10, pady=10)

		button4 = ttk.Button(self, text="PATS", command=lambda: controller.show_frame(Page4))
		button4.grid(row=4, column=5, padx=10, pady=10)


# second window frame page1
class Page1(tk.Frame):

	def __init__(self, parent, controller):
		tk.Frame.__init__(self, parent)
		label = ttk.Label(self, text="Page 1", font=LARGEFONT)
		label.grid(row=0, column=4, padx=10, pady=10)

		# button to show frame 2 with text
		# layout2
		button1 = ttk.Button(self, text="StartPage", command=lambda: controller.show_frame(Start_Page))

		# putting the button in its place
		# by using grid
		button1.grid(row=1, column=1, padx=10, pady=10)

		# button to show frame 2 with text
		# layout2
		button2 = ttk.Button(self, text="Page 2", command=lambda: controller.show_frame(Page2))

		# putting the button in its place by
		# using grid
		button2.grid(row=2, column=1, padx=10, pady=10)


# third window frame page2
class Page2(tk.Frame):
	def __init__(self, parent, controller):
		tk.Frame.__init__(self, parent)
		label = ttk.Label(self, text="Page 2", font=LARGEFONT)
		label.grid(row=0, column=4, padx=10, pady=10)

		# button to show frame 2 with text
		# layout2
		button1 = ttk.Button(self, text="Page 1", command=lambda: controller.show_frame(Page1))

		# putting the button in its place by
		# using grid
		button1.grid(row=1, column=1, padx=10, pady=10)

		# button to show frame 3 with text
		# layout3
		button2 = ttk.Button(self, text="Start_page", command=lambda: controller.show_frame(Start_Page))

		# putting the button in its place by
		# using grid
		button2.grid(row=2, column=1, padx=10, pady=10)

class Page3(tk.Frame):

	def __init__(self, parent, controller):
		tk.Frame.__init__(self, parent)
		label = ttk.Label(self, text="Page 1", font=LARGEFONT)
		label.grid(row=0, column=4, padx=10, pady=10)

		# button to show frame 2 with text
		# layout2
		button1 = ttk.Button(self, text="StartPage", command=lambda: controller.show_frame(Start_Page))

		# putting the button in its place
		# by using grid
		button1.grid(row=1, column=1, padx=10, pady=10)

		# button to show frame 2 with text
		# layout2
		button2 = ttk.Button(self, text="Page 2", command=lambda: controller.show_frame(Page2))

		# putting the button in its place by
		# using grid
		button2.grid(row=2, column=1, padx=10, pady=10)

class Page4(tk.Frame):

	def __init__(self, parent, controller):
		tk.Frame.__init__(self, parent)
		label = ttk.Label(self, text="Page 1", font=LARGEFONT)
		label.grid(row=0, column=4, padx=10, pady=10)

		# button to show frame 2 with text
		button1 = ttk.Button(self, text="StartPage", command=lambda: controller.show_frame(Start_Page))

		# putting the button in its place
		# by using grid
		button1.grid(row=1, column=1, padx=10, pady=10)

		# button to show frame 2 with text
		# layout2
		button2 = ttk.Button(self, text="Page 2", command=lambda: controller.show_frame(Page2))

		# putting the button in its place by
		# using grid
		button2.grid(row=2, column=1, padx=10, pady=10)


# Driver Code
app = tkinterApp()
app.mainloop()
