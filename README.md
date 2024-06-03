from datetime import datetime

name = input("Enter your name :")

#List of Items 
list = '''
Rice              Rs 50/kg
Sugar             Rs 20/kg
Salt              Rs 15/kg
Maggie            Rs 12/each
Chilli Powder     Rs 18/kg
Soups             Rs 10/each
Tooth Paste       Rs 25/each
Brush             Rs 10/each
Oil               Rs 85/litre
Paneer            Rs 45/each
Chocolates        Rs 15/each 
'''

#Declaration
price = 0
pricelist = []
totalprice = 0
finalprice = 0
ilist = []
qlist = []
plist = []

#Rates of Items
items = {'rice':50,'sugar':20,'salt':15,'maggie':12,'chilli powder':18,'soups':10,
'tooth paste':25,'brush':10,'oil':85,'paneer':45,'chocolates':15}

option = int(input("To show the list of items press 1 :"))
if option == 1:
    print(list)
for i in range(len(items)):
    inp1 = int(input("If you want to buy press 1 or press 2 for 'exit' :"))
    if inp1 == 2:
        break
    if inp1 == 1:
        item = input("Enter your items :")
        quantity = int(input("Enter Quantity :"))
        if item in items.keys():
            price = quantity*(items[item])
            pricelist.append((item,quantity,items,price))
            totalprice += price
            ilist.append(item)
            qlist.append(quantity)
            plist.append(price)
            gst =  (totalprice*5)/100
            finalprice = gst + totalprice
        else:
            print("Sorry you entered item is 'not' available")
    else:
        print("You entered 'wrong' number")

inp = input("If you want the 'bill' type 'yes' or you don't want the 'bill' type 'no' :")
if inp == 'yes':
    pass
    if finalprice != 0:
        print(30*"-","D-Mart",34*"-")
        print(27*" ","Visakhapatnam")
        print("Name:",name,30*" ","Date:",datetime.now())
        print(73*"-")
        print("S.no",14*" ","Items",14*" ","Quantity",14*" ","Price")
        for i in range(len(pricelist)):
            print(i,17*" ",ilist[i],17*" ",qlist[i],17*" ",plist[i])
        print(73*"-")
        print("Total Amount:",48*" ","Rs",totalprice)
        print("GST Amount:",50*" ","Rs",gst)
        print(73*"-")
        print("Final Amount:",48*" ","Rs",finalprice)
        print(73*"-")
        print(25*" ","Thanks for Visiting :)",27*" ")
        print(73*"-")





 
