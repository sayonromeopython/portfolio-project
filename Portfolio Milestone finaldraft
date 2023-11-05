#romeo Sayon
#CSU Global
# Portfolio Milestone/Online Shopping Cart
# November 04, 2023
class ItemToPurchase:
  def __init__(self, name="none", price=0.0, quantity=0, description="none"):
      self.name = name
      self.price = price
      self.quantity = quantity
      self.description = description

  def print_item_cost(self):
      print(f"{self.name} {self.quantity} @ ${self.price} = ${self.price * self.quantity}")

class ShoppingCart:
  def __init__(self, customer_name="none", current_date="January 1, 2020"):
      self.customer_name = customer_name
      self.current_date = current_date
      self.cart_items = []

  def add_item(self, item):
      self.cart_items.append(item)

  def remove_item(self, item_name):
      found = False
      for item in self.cart_items:
          if item.name == item_name:
              self.cart_items.remove(item)
              found = True
              break
      if not found:
          print("Item not found in cart. Nothing removed.")

  def modify_item(self, item):
      found = False
      for cart_item in self.cart_items:
          if cart_item.name == item.name:
              if item.price != 0.0:
                  cart_item.price = item.price
              if item.quantity != 0:
                  cart_item.quantity = item.quantity
              if item.description != "none":
                  cart_item.description = item.description
              found = True
              break
      if not found:
          print("Item not found in cart. Nothing modified.")

  def get_num_items_in_cart(self):
      total_quantity = sum(item.quantity for item in self.cart_items)
      return total_quantity

  def get_cost_of_cart(self):
      total_cost = sum(item.price * item.quantity for item in self.cart_items)
      return total_cost

  def print_total(self):
      if not self.cart_items:
          print("SHOPPING CART IS EMPTY")
      else:
          print(f"{self.customer_name}'s Shopping Cart - {self.current_date}")
          print(f"Number of Items: {self.get_num_items_in_cart()}\n")
          for item in self.cart_items:
              item.print_item_cost()
          print(f"\nTotal: ${self.get_cost_of_cart()}")

  def print_descriptions(self):
      print(f"{self.customer_name}'s Shopping Cart - {self.current_date}\nItem Descriptions:")
      for item in self.cart_items:
          print(f"{item.name}: {item.description}")

def print_menu(cart):
  print("\nMENU")
  print("a - Add item to cart")
  print("r - Remove item from cart")
  print("c - Change item quantity")
  print("i - Output items' descriptions")
  print("o - Output shopping cart")
  print("q - Quit")

def output_shopping_cart(cart):
  print("OUTPUT SHOPPING CART")
  cart.print_total()

def output_item_descriptions(cart):
  print("OUTPUT ITEMS' DESCRIPTIONS")
  cart.print_descriptions()

if __name__ == "__main__":
  customer_name = input("Enter the customer's name: ")
  purchase_date = input("Enter today's date : ")

  
  cart = ShoppingCart(customer_name, purchase_date)

  
  print(f"Customer's Name: {cart.customer_name}")
  print(f"Today's Date: {cart.current_date}")

  while True:
      print_menu(cart)
      choice = input("Choose an option: ")

      if choice == "a":
          item = ItemToPurchase(input("Add Item to Cart\nEnter the item name: "),
                                float(input("Enter the item price: ")),
                                int(input("Enter the item quantity: ")),
                                input("Enter the item description: "))
          cart.add_item(item)
      elif choice == "r":
              item_name = input("REMOVE ITEM FROM CART\nEnter name of item to remove: ")
              cart.remove_item(item_name)
      elif choice == "c":
              item_name = input("CHANGE ITEM QUANTITY\nEnter the item name: ")
              new_quantity = int(input("Enter the new quantity: "))
              new_item = ItemToPurchase(item_name, 0, new_quantity)
              cart.modify_item(new_item)
      elif choice == "i":
              output_item_descriptions(cart)
      elif choice == "o":
              output_shopping_cart(cart)
      elif choice == "q":
              break
      else:
              print("Invalid option. Please try again.")
