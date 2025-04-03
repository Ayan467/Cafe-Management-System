# Cafe-Management-System
# Using Python



class MenuItem: 
def __init__(self, name, price): 
self.name = name 
self.price = price 
class Cafe: 
def __init__(self): 
self.menu = [] 
self.orders = [] 
self.revenue = 0 
def add_menu_item(self, name, price): 
item = MenuItem(name, price) 
self.menu.append(item) 
print(f"Added {name} to menu for ${price}") 
def show_menu(self): 
print("\nCafe Menu:") 
for idx, item in enumerate(self.menu, start=1): 
print(f"{idx}. {item.name} - ${item.price}") 
def take_order(self): 
self.show_menu() 
try: 
            choice = int(input("Enter item number to order: ")) - 1 
            if 0 <= choice < len(self.menu): 
                self.orders.append(self.menu[choice]) 
                print(f"{self.menu[choice].name} added to order.") 
            else: 
                print("Invalid selection. Please enter a valid menu number.") 
        except ValueError: 
            print("Invalid input! Please enter a number.") 
 
    def generate_bill(self): 
        print("\nBill Summary:") 
        total = 0 
        for item in self.orders: 
            print(f"{item.name} - ${item.price}") 
            total += item.price 
        print(f"Total: ${total}") 
        self.revenue += total 
        self.orders = []  # Clear orders after billing 
 
    def show_revenue(self): 
        print(f"Total Revenue: ${self.revenue}") 
 
# Sample execution 
if __name__ == "__main__": 
    cafe = Cafe() 
    cafe.add_menu_item("Coffee", 3.5) 
    cafe.add_menu_item("Tea", 2.5) 
    cafe.add_menu_item("Sandwich", 5.0) 
     
    while True: 
        print("\n1. Show Menu\n2. Take Order\n3. Generate Bill\n4. Show Revenue\n5. Exit") 
        option = int(input("Choose an option: ")) 
        if option == 1: 
cafe.show_menu() 
elif option == 2: 
cafe.take_order() 
elif option == 3: 
cafe.generate_bill() 
elif option == 4: 
cafe.show_revenue() 
elif option == 5: 
print("Exiting...") 
break 
else: 
print("Invalid choice. Try again.") 
