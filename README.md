# A travel agency wants a catalog to keep track of the destinations (cities)
# they provide trips to. They want applications to:
# 1. Add city
# 2. Display cities
# 3. Check if city is destination
# 4. Delete city
# 5. Display the number of cities

cities = []

def display_menu() -> None:
    print("1. Add City")
    print("2. Display Cities")
    print("3. Check if City is Destination ")
    print("4. Delete City")
    print("5. Display the number of cities")

def get_user_choice() -> int:
    try:
        choice = int(input("Choose one of the following: "))
    except ValueError:
        return -1
    return choice 

def add_city(c:list[str]) -> None:
        name = input("Please give a name of the city: ")
        if name in c:
             print("The name of the city is already in the list")
             return
        else:
             print("City Accepted")
             return -1
        
def display_cities(c:list[str]) -> None:
     if c in cities:
          print(cities)
     else:
          print("An error showed up.")

             
def destination_of_the_city(c:list[str]) -> None:
     destination = input("Give us a following destination that you would like: ")
     try:
          if destination in c:
               return None
          else:
               return -1 
          return destination
     except ValueError:
          return destination
     return -1

def if_city_is_a_destination(c:list[str]) -> None:
     destination = destination_of_the_city(c)
     if destination == if_city_is_a_destination:
          for i in range(len(c)):
               if c[i] == destination:
                    print("It is indeed a destination!")
               else:
                    print("It is not a destination!")
                         
def get_existing_name(c:list[str]) -> None:
     name = input("Give name of the city: ")
     try:
          if name not in c:
               return None
          else:
               return name
          return -1
     except ValueError:
          return name 
     return -1

def delete_city(c:list[str]) -> None:
     name = get_existing_name(c)
     if name is not None:
          for i in range(len(c)):
               if c[i] == name:
                    del c[i]
                    break

while True:
     display_menu()
     choice = get_user_choice()
     if choice == 1:
          add_city(cities)
     elif choice == 2:
          display_cities(cities)
     elif choice == 3:
          if_city_is_a_destination(cities)
     elif choice == 4:
          delete_city(cities)
     elif choice == 0:
          print("Goodbye for now!")
          break
     else:
          print("Wrong choice.Oops!")
        
