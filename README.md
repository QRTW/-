import turtle

# Настройки окна
turtle.bgcolor("deepskyblue")
turtle.title("Дом с дымоходом")

# Функция для рисования зелёной поляны
def draw_grass():
    turtle.penup()
    turtle.goto(-400, -100)
    turtle.pendown()
    turtle.color("green")
    turtle.begin_fill()
    for _ in range(2):
        turtle.forward(800)
        turtle.right(90)
        turtle.forward(200)
        turtle.right(90)
    turtle.end_fill()

# Функция для рисования крыши
def draw_roof():
    turtle.penup()
    turtle.goto(-110, 60)
    turtle.pendown()
    turtle.color("saddlebrown")
    turtle.begin_fill()
    turtle.goto(0, 200)
    turtle.goto(110, 60)
    turtle.end_fill()

# Функция для рисования дома
def draw_house():
    turtle.penup()
    turtle.goto(-100, -140)  # Смещение дома чуть ниже
    turtle.pendown()
    turtle.color("darkorange")
    turtle.begin_fill()
    for _ in range(4):
        turtle.forward(200)
        turtle.left(90)
    turtle.end_fill()

    turtle.penup()
    turtle.goto(-30, -140)
    turtle.pendown()
    turtle.color("saddlebrown")
    turtle.begin_fill()
    for _ in range(2):
        turtle.forward(60)
        turtle.left(90)
        turtle.forward(120)
        turtle.left(90)
    turtle.end_fill()

    # Рисуем дверную ручку
    turtle.penup()
    turtle.goto(-20, -80)  # Середина правой стороны двери
    turtle.pendown()
    turtle.color("black")
    turtle.pensize(3)
    turtle.forward(5)  # Длина ручки
    turtle.penup()
    turtle.goto(-20, -80)
    turtle.pendown()
    turtle.right(90)
    turtle.forward(5)  # Ширина ручки
    turtle.penup()
    turtle.goto(-20, -80)
    turtle.pendown()
    turtle.left(90)
    turtle.forward(5)

    draw_window(-80, -20, "deepskyblue")

def draw_window(x, y, color):
    # Рисуем окно
    turtle.penup()
    turtle.goto(x, y)
    turtle.pendown()
    turtle.color(color)
    turtle.begin_fill()
    for _ in range(4):
        turtle.forward(40)
        turtle.left(90)
    turtle.end_fill()

    # Рисуем вертикальную линию на окне (крест)
    turtle.penup()
    turtle.goto(x + 20, y + 40)
    turtle.pendown()
    turtle.color("black")
    turtle.goto(x + 20, y - 0)

    # Рисуем горизонтальную линию на окне (крест)
    turtle.penup()
    turtle.goto(x - 0, y + 20)
    turtle.pendown()
    turtle.goto(x + 40, y + 20)

def draw_chimney():
    turtle.penup()
    turtle.goto(40, 115)  # Переместили дымоход ниже
    turtle.pendown()
    turtle.color("gray")
    turtle.begin_fill()
    for _ in range(2):
        turtle.forward(20)
        turtle.left(90)
        turtle.forward(60)
        turtle.left(90)
    turtle.end_fill()

    # Рисуем дым
    turtle.penup()
    turtle.goto(55, 185)  # Начальная позиция дыма
    turtle.pendown()
    turtle.color("lightgray")
    turtle.begin_fill()
    turtle.circle(10)
    turtle.end_fill()

    # Рисуем круги от дымохода
    draw_smoke_circle(55, 185, 10)
    draw_smoke_circle(70, 210, 15)
    draw_smoke_circle(90, 250, 20)

def draw_smoke_circle(x, y, radius):
    turtle.penup()
    turtle.goto(x, y)
    turtle.pendown()
    turtle.color("lightgray")
    turtle.begin_fill()
    turtle.circle(radius)
    turtle.end_fill()

draw_grass()
draw_roof()
draw_house()
draw_chimney()
turtle.exitonclick()
