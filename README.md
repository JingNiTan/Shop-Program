# Shop-Program
This program will help to calculate total amount, average, find the most expensive and cheapest product.
#inputs
print("Shop Program")
name = input("Please enter name: ")
print(f"Welcome {name}!")
#make lists
productlist = []
pricelist = []
qtylist = []
totallist = []
#make loop and inputs
while True:
    product = input("Please enter product name: ")
    try:
        price = float(input("Please enter price: $"))
        qty = int(input("Please enter quantity: "))
    except ValueError:
        print("Invalid input. Please enter a valid number.")
        continue
#append the new information
    productlist.append(product)
    pricelist.append(price)
    qtylist.append(qty)
    totallist.append(price*qty)
#ask if they want to continue
    answer = input("Do you want to continue(yes/no)? ")
    if answer != "yes":
        break
#calculate all information
total = sum(totallist)
average = total/sum(qtylist)

highest_price = max(pricelist)
lowest_price = min(pricelist)

index_highest = pricelist.index(highest_price)
highest_sales_product = productlist[index_highest]

index_lowest = pricelist.index(lowest_price)
lowest_sales_product = productlist[index_lowest]
#print all information
print(f"Total: ${total:0.2f}")
print(f"Average: ${average:0.2f}")
print(f"Most Expensive Product: {highest_sales_product}")
print(f"Highest Price: ${highest_price:0.2f}")
print(f"Cheapest Product: {lowest_sales_product}")
print(f"Lowest Product: ${lowest_price:0.2f}")
