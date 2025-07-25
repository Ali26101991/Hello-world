class BalanceExceptionError(Exception):
    pass

class AttemptsExceptionError(Exception):
    pass

attempts=1
def withdraw():
    saved_pin=1234
    balance=200000
    global attempts
    pin=int(input("enter the pin : "))
    if pin==saved_pin:
        amt=float(input("enter the desired amount :"))
        temp_balance=balance-amt
        try:
            if temp_balance<1000:
                raise BalanceExceptionError("insuffienct fund")

            else:
                balance=balance-amt
                print("the remaining balance is :",balance)

        except Exception as var:
            print(var)

    else:
        res=input("do you want to continue (y/n):")
        if res.lower()=="y":
            attempts+=1
            try:
                if attempts==4:
                    raise AttemptsExceptionError("To many attempts , account will be blocked for an hour")

            except Exception as var:
                print(var)
            else:
                withdraw()

        else:
            print("Thank you ! visit again")






withdraw()

