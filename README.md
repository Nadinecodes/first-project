# first-project
#This is a simple plant shop that lets you choose some plants and give you a total cost
low_light={
"Pathos": 7,
"Peace Lily":15,
"ZZ Plant":6,
"Alocasia Polly":20
}
sun_lovers={
"Aloe":3,
"Cactus":5,
"Croton":15,
"Palm":12,
"Fiddle-leaf Fig":80
}
all=dict(low_light,**sun_lovers)
allprice=[all]    
cart=[]
cart_total=[]

#Check the type of plants customer wants
def plant_type(y):
    if preference=="low light":
        print("Great! We have the following selections:")
        for i in low_light:
            print(i) 
    elif preference=="sun loving":
        print("Ok we have the following:")  
        for s in sun_lovers:
            print(s)
    elif preference== "both":
           for key in all:
               print(key,"-",all[key])
    else:
        print("Sorry, we do not have that. Please select from our lists")

#Get customer's selections
def choices(c):
    if choice in low_light:
        cart.append(choice)
    elif choice in sun_lovers:  
        cart.append(choice)
           
    else:
        print("Sorry we don't not have that plant. Please choose an item from our list of plants") 
    print("Your item was added to your shopping cart") 

#check if customer is finish shopping   
def done_shopping():
    x=input("Will that be all? Type yes or no: ")
    while True:
        if x=="no":
            ans2=input("What else you would like? Choose from our list of plants: ")
            cart.append(ans2)
            x=input("Are you done now? ")
            continue
        if x=="yes":
            break
    print("Great! Let's go to yourshopping cart")

#Get total
def total():
        for i in all:
            for j in cart:
                if j in i:
                    price=all[j]
                    cart_total.append(price)

print("Welcome to Nadine's plant shop. My name is Greenbot and I'm here to assist you today.")
age=int(input("How old are you? "))
if age<16:
    print("Sorry, you need an adult present to make a purchase")
else:
    print("Great!")

print("Our store is divided into 2 sections:low light plants, and sun loving plants.") 
preference=input("What kind of plant are you looking for? You maybe enter low light, Sun loving, or both. ").lower()
plant_type(preference) 
choice=input("Which would you like? ")
choices(choice)
done_shopping()  
print("Here's what's in your cart")
for items in cart:
    print(items)
total()
print("Your total is $",sum(cart_total))      



