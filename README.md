Functions
=========

Functions written in Python for CS 1301. Some of them interact with the Scribbler 2 and Fluke 2.

from Graphics import *

def face():
    win = Window("Face", 600, 600)
    circle = Circle((300, 300), 260)
    circle.fill = makeColor("pink")
    circle.draw(win)
    lefteye = Circle((200, 250), 45)
    lefteye.fill = makeColor("green")
    lefteye.draw(win)
    righteye = Circle((400, 250), 45)
    righteye.fill = makeColor("green")
    righteye.draw(win)
    nose = Polygon((250,340), (350, 340), (300, 390))
    nose.fill = makeColor("lightblue")
    nose.draw(win)
    smile = Curve((200, 405), (250, 450), (350, 450), (400,405))
    smile.draw(win)
    hatbrim = Line((10, 175), (590, 175))
    hatbrim.draw(win)
    tophat = Polygon((70, 175), (530, 175), (530, 25), (70, 25))
    tophat.fill = makeColor("black")
    tophat.draw(win)

def machToFPS():
    toConvert = float(input("Enter the speed in mach"))
    x = toConvert
    f = (1116.4370079 * x)
    f == (1116.4370079 * x)
    print (f, "feet per second")


def sqPyramidVolume():
    baseLength = float(input("What is the length of one side of the base in inches?"))
    b = baseLength
    height = float(input("What is the height of the pyramid in inches?"))
    h = height
    v = ((b * b * h) / 3)
    print ("The volume of the square pyramid is", v, "cubic inches")


def makeChange():
    c = int(input("How many cents?"))
    d = (c // 100)
    q = (((c - (d * 100)) // 25))
    i = (((c - (d * 100) - (q * 25)) // 10))
    n = (((c - (d * 100) - (q * 25) - (i * 10)) // 5))
    p = (c - (d * 100) - (q * 25) - (i * 10) - (n * 5))
    print (c, "cents makes", d, "dollars", q, "quarters,", i, "dimes,", n, "nickles, and", p, "pennies.")


def PPIIndex():
    p = float(input("How much do you weigh in pounds?"))
    h = float(input("How tall are you in inches?"))
    x = (p / h * 1.125)
    print ("Your correct PPI is %.1f." % x)
    
def quesoForFishy(accmoney):
    pJar = 2.98
    amtJar = accmoney/2.98
    amtJar = int(amtJar)
    return amtJar

def mailBoxes(numHit):
    lowPrediction = numHit*2
    highPrediction = numHit*6
    print("Because you have hit " + str(numHit) + " mailboxes. Your car's life has most likely been shortened by " + str(lowPrediction) + " to " + str(highPrediction) + " months.")

from math import *
def concertTicket():
    price = input("What is the price of the ticket you want?")
    money = input("How much money do you make per hour?")
    tHours = float(price)/float(money)
    round(tHours, 2)
    print("You need to work %.2f"%tHours)
    
def boringInterlude(rad):
    """enter radius in inches please"""
    rad = float(rad)
    feet = (rad / 12)
    vol = float((4/3)*pi*feet*feet*feet)
    return vol
    """returns volume in cubic feet"""


def trafficJam(x, y):
    # x = number of lanes
    # y = number of miles
    if (x % 1) > 0:
        raise TypeError, "number of lanes must be an integer."
    a = ((x * (y * 5280)) / 15)
    return (a)

def timeLeft(f):
    # f = amount of time you have used your flashlight in minutes
    if (f % 1) > 0:
        raise TypeError, "f must be an integer"
    x = float(input("How many hours does the flashligh battery last?"))
    print ((((x - (f / 60)) / x) * 100) // 1)
    return ((x * 60) - f)

def daffodils(f, c, p):
    import math
    # f = number of flowers that need to be planted
    # c = amount of money your neighbor will contribute
    # p = price of 12 flowers
    # b = number of sets of 12 flowers needed
    if (f % 1) > 0:
        raise TypeError, "f must be an integer."
    b = math.ceil(f / 12)
    x = ((b * p) - c)
    print ("You will need to contribute $%.2f" % x)


from Myro import *

init()

def avoidWalls():
    for seconds in timer(60):
        if getObstacle("left") > 5500:
            turnRight(1, .75)
        elif getObstacle("right") > 5500:
            turnLeft(1, .75)
        elif getObstacle("center") > 5500:
            turnLeft(1, .75)
        else:
            translate(1)
    stop()
    beep(.5, 800)
    beep(.5, 400)
    beep(1, 700)
    beep(1, 900)
    
def tallEnough(inches):
    inches = int(inches)
    inches = inches / 0.39370
    if 120 < inches < 190:
        return True
    else:
        return False

def whereIsWaldo(Int1, Int2):
    Int1 = int(Int1)
    Int2 = int(Int2)
    x = int(input("Guess Waldo's x-coordinate."))
    y = int(input("Guess Waldo's y-coordinate."))
    if (Int1 == x) and (Int2 == y):
        return "You found Waldo."
    else:
        return "Couldn't find Waldo. Better luck next time."

def allLetters(userString):
    import string
    userString = str(userString)
    valids = []
    for character in userString:
        if character in string.ascii_letters:
            valids.append(character)
    return ''.join(valids)

def replaceLetter(aString, aLetter):
    import string
    aString = str(aString)
    aLetter = str(aLetter)
    new = []
    x = input(str("Input one letter from your string"))
    while x not in aString:
        x = input(str("Letter is not in string. Input one letter from your string."))
    for character in aString:
        y = character
        if character in x:
            y = aLetter
        new.append(y)
    return ''.join(new)

def countUp(x, y, z):
    x = int(x)
    y = int(y)
    z = int(z)
    for number in range(x, y+1, z):
        print (number)

from Myro import *
init()


def Fetch():
    turnRight (1, 1.3)
    forward(1, 3)
    turnRight (1, 1.3)
    forward(1, 3)

def chaseTail():
    turnRight(1, 10.4)

def Crawl():
    for seconds in timer(25):
        if getObstacle("left") > 5500:
            turnRight(1, .75)
        elif getObstacle("right") > 5500:
            turnLeft(1, .75)
        elif getObstacle("center") > 5500:
            turnLeft(1, .75)
        else:
            translate(.15)
    stop()

def Speak():
    beep(.5, 600)
    beep(.5, 470)
    beep(.5, 600)

def Greeting():
    beep(.25, 698.46)
    beep(.25, 880)
    beep(.5, 987.77)
    beep(.25, 698.46)
    beep(.25, 880)
    beep(.5, 987.77)
    beep(.25, 698.46)
    beep(.25, 880)
    beep(.25, 987.77)
    beep(.25, 1318.51)
    beep(.5, 1174.66)
    beep(.25, 987.77)
    beep(.25, 1047.5)
    beep(.25, 987.77)
    beep(.25, 783.99)
    beep(1.25, 659.25)
    beep(.25, 587.33)
    beep(.25, 659.25)
    beep(.25, 783.99)
    beep(1.5, 659.25)

def morningRoutine(x):
    if x >= 5:
        Greeting()
    if x >= 4:
        Speak()
    if x >= 3:
        Crawl()
    if x >= 2:
        chaseTail()
    if x >= 1:
        Fetch()

def greetMenu():
    print ("1. Small treat")
    print ("2. Medium treat")
    print ("3. Large treat")
    print ("0. Exit")
    y = (float(input("Which option would you like?")))
    if y == 1:
        Crawl()
        Speak()
    elif y == 2:
        chaseTail()
        Crawl()
        Speak()
        Fetch()
    elif y == 3:
        chaseTail()
        Crawl()
        Speak()
        Fetch()
        Greeting()
    elif y == 0:
        print ("Bye bye! Have a nice day!")
        greetMenu()
        
from Myro import *
from Graphics import *
init()
#Part One and Part Two
myCanvas = Window("Robot",0,0)
myFile = open("myMovements.txt", "a")



def getLightSensor():
    x = getLight("right")
    y = getLight("left")
    z = (y/(x+y))
    myFile.write(str(z))

def handleKeyRelease(win,event):
        if(event.key == "Up"):
            forward(1,.1)
            myFile.write("Forward (1,.1)")
            getLightSensor()
        elif(event.key == "Down"):
            backward(1,.1)
            myFile.write("Backward (1,.1)")
            getLightSensor()
        elif(event.key == "Right"):
            turnRight(1,1)
            myFile.write("Right-turn (1,.1)")
            getLightSensor()
        elif(event.key == "Left"):
            turnLeft(1,1)
            myFile.write("Left-turn (1,.1)")
            getLightSensor()
        elif(event.key == "b"):
            beep(1,800)
            myFile.write("Beep (1,800)")
        else:
            myFile.close()
onKeyPress(handleKeyRelease)




#Part 3
def collectData(nameFile,direction):
    theFile = open(nameFile,"r")
    time = 0.0
    timFor = 0
    timBac = 0
    timRig = 0
    timLef = 0
    beep = 0
    z = 0.0
    lines = theFile.readlines()
    for y in lines:
        hi = y.split()
        if(hi[0] == "Forward" or hi[0] == "Backward"): #For Total Time Traveled
            time += .1
        if(hi[0] == "Forward"): #For time going forward
            timFor += 1
        elif(hi[0] == "Backward"): #For time going backward
            timBac += 1
        elif(hi[0] == "Leftturn"): #For time
            timLef += 1
        elif(hi[0] == "Rightturn"):
            timRig += 1
        elif(hi[0] == "Beep"):
            beep += 1
        if(direction == "Forward"):
            z = timFor
        elif(direction == "Backward"):
            z = timBac
        elif(direction == "Right"):
            z = timRig
        elif(direction == "Left"):
            z = timLef
        # closes the file and returns the statement
    theFile.close()
    return("The robot traveled for " + str(time) + " seconds total, beeping "  +  str(beep) + " times. This robot moved " + str(direction)+ " a total of " + str(z) + " times.")




#Part 4
def rePlay(whatFile):
    c = open(whatFile,"r")
    nlines = c.readlines()
    for p in nlines:
        a = p.split()
        if(a[0] == "Forward"):
            forward(1,.1)
        if(a[0] == "Backward"):
            backward(1,.1)
        if(a[0] == "Rightturn"):
            turnRight(1,1)
        if(a[0] == "Leftturn"):
            turnLeft(1,1)
        if(a[0] == "Beep"):
            beep(1,800)
    c.close()
    
from Myro import *
init()


def getValues(x):
    v = []
    x = int(x)
    while x > 0:
        getLight('center')
        turnLeft(1, .25)
        x = x - 1
        y = (getLight('center'))
        v.append(y)
    return v

def getStatistics(z = []):
    e = []
    a = len(z)
    b = max(z)
    c = min(z)
    d = sum(z)/len(z)
    for i in z:
        if i % 2 == 0:
            e.append(i)
    f = len(e)
    print ("You gave me a list of", a, "numbers. Their average was", d,". The largest was", b,", the smallest was", c, ". Only", f,"of them were even numbers.")
