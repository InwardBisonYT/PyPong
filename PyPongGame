import turtle

#Window setup
mainWidnow = turtle.Screen()
mainWidnow.title("Pong by BisonDoesDev")
mainWidnow.bgcolor("black")
mainWidnow.setup(width=800, height=600)
mainWidnow.tracer(0)

#Paddle A
paddleA = turtle.Turtle()
paddleA.speed(0)
paddleA.shape("square")
paddleA.color("white")
paddleA.shapesize(stretch_wid=5, stretch_len=1)
paddleA.penup()
paddleA.goto(-350,0)

#paddle B
paddleB = turtle.Turtle()
paddleB.speed(0)
paddleB.shape("square")
paddleB.color("white")
paddleB.shapesize(stretch_wid=5, stretch_len=1)
paddleB.penup()
paddleB.goto(350,0)

#ball
ball = turtle.Turtle()
ball.speed(0)
ball.shape("circle")
ball.color("white")
ball.penup()
ball.goto(0,0)
ball.dx = 5
ball.dy = 5

#socre
pen = turtle.Turtle()
pen.speed(0)
pen.color("white")
pen.penup()
pen.hideturtle()
pen.goto(0,260)
pen.write("Player A: 0  Player B: 0", align="center", font=("Courier", 20, "underline"))
scoreA = 0
scoreB = 0

def paddleA_UP():
    y = paddleA.ycor()
    y += 20
    paddleA.sety(y)

def paddleA_DOWN():
    y = paddleA.ycor()
    y -= 20
    paddleA.sety(y)

def paddleB_UP():
    y = paddleB.ycor()
    y += 20
    paddleB.sety(y)

def paddleB_DOWN():
    y = paddleB.ycor()
    y -= 20
    paddleB.sety(y)

#keybinds
mainWidnow.listen()
mainWidnow.onkeypress(paddleA_UP, "w")
mainWidnow.onkeypress(paddleA_DOWN, "s")
mainWidnow.onkeypress(paddleB_UP, "Up")
mainWidnow.onkeypress(paddleB_DOWN, "Down")

while True:
    mainWidnow.update()
    ball.setx(ball.xcor()+ball.dx)
    ball.sety(ball.ycor()+ball.dy)
    if ball.ycor() > 290:
        ball.sety(290)
        ball.dy *= -1
    if ball.ycor() < -290:
        ball.sety(-290)
        ball.dy *= -1
    if ball.xcor() > 390:
        ball.goto(0,0)
        ball.dx = -0.2
        scoreA += 1
        pen.clear()
        pen.write(f"Player A: {scoreA} PlayerB: {scoreB}", align="center", font=("Courier",20,"underline"))
    if ball.xcor() < -390:
        ball.goto(0,0)
        ball.dx = +0.2
        scoreB += 1
        pen.clear()
        pen.write(f"Player A: {scoreA} PlayerB: {scoreB}", align="center", font=("Courier",20,"underline"))
    if (ball.xcor() >340 and ball.xcor() < 350) and (ball.ycor() < paddleB.ycor()+40 and ball.ycor() > paddleB.ycor()-40):
        ball.setx(340)
        ball.dx *= -1
    if (ball.xcor() <-340 and ball.xcor() >-350) and (ball.ycor() < paddleA.ycor()+40 and ball.ycor() > paddleA.ycor()-40):
        ball.setx(-340)
        ball.dx *= -1
