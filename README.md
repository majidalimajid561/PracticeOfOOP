# PracticeOfOOP
class Students:
     
    def __init__(self,name,roll,Depart):
        self.name=name
        self.roll=roll
        self.Depart=Depart
    def info(self):
        print(self.name)
        print(self.roll)
        print(self.Depart) 

# class for fractions visulizations 

class Fraction:
    def __init__(self,x,y):
        self.num=x
        self.den=y
    def __str__(self):
        return "{}/{}".format(self.num,self.den)
    def __add__(self,othrer):
        newnum=self.num*othrer.den+self.den*othrer.num
        newden=self.num+othrer.den
        return "{}/{}".format(newnum,newden)
    def __sub__(self,othrer):
        newnum=self.num*othrer.den-self.den*othrer.num
        newden=self.num+othrer.den
        return "{}/{}".format(newnum,newden)
    def __mul__(self,othrer):
        newnum=self.num*othrer.num
        newden=self.den+othrer.den
        return "{}/{}".format(newnum,newden)
    def __truediv__(self,othrer):
        newnum=self.num*othrer.den
        newden=self.den+othrer.num
        return "{}/{}".format(newnum,newden)
# custion Exceptions class

# class MyException(Exception):
#     def __init__(self,info):
#         print(info)

# def division(num,den):
#     if type(num)!=int or type(den)!=int:
#         raise MyException("ary bhai number input do")
#     if den==0:
#         raise Exception("denoirator zero ha ")
#     return num/den
# try:
#     division(1,'ll')
# except MyException as e:
#     pass
# except Exception as e:
#     pass

class Atm:
    def __init__(self,pin,balance):
       self.pin=pin
       self.balance=balance

    def pin_verfiy(self):
        for attempts  in range(3):
            enter_pin=int(input("Enter pin \n"))
            if enter_pin==self.pin:
                return True
            else:
                print("try again")
                attempts+=1
        print("Too many failed attempts. Exiting.")
        return False
    

    def ShowBalance(self):
        if self.pin_verfiy:
          print("you have ")
          print(self.balance)
        


    def AddAmount(self):
        print("Enter Amount")
        try:
         amount =float(input())
         if amount<0:
            print("Enter positive amount")
         else: 
          self.balance+=amount
          print("Amount add successfully")
        except ValueError:
           print("Invalid inPut! Please enter a povitive number")




    def WithDraw(slef):
        print("Enter amoutn for with draw")
        try:
         amount =float(input())
         if amount>slef.balance:
            print("You have not enough amount to withraw")
         elif amount<=0:
            print("Enter positive amount")
         else:
            slef.balance-=amount
            print("amount withDraw Successfully")
        except ValueError:
             print("Invalid Amount")


    def menu(self): 
     # showbalanc
        print("Welcome to Majid's jugado ATM ")
        if self.pin_verfiy()!=True:
            return
        while True:
          print("enter 1 to see balance")
          print("Enter 2 to add balance")
          print("Enter 3 to withdraw")
          print("enter 4 to exist")
          n =int(input())
          if n==1:
            self.ShowBalance()
          elif n==2:
            self.AddAmount()
          elif n==3:
            self.WithDraw()
          else:
            break 
