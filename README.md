# Personal-library
class Book:
  def __init__(self, name, topic):
    self.name = name
    self.topic = topic

  def print_info(self):
    print("Book Name:", self.name)
    print("Topic:", self.topic)


class Library:
  def __init__(self):
    self.books = []

  def add_book(self, name, topic):
    new_book = Book(name, topic)
    self.books.append(new_book)
    print("Book added successfully.")

  def remove_book(self, name):
    for book in self.books:
      if book.name == name:
        self.books.remove(book)
        print("Book removed successfully.")
        return
    print("Book not found.")

  def modify_book(self, name, new_name, new_topic):
    for book in self.books:
      if book.name == name:
        book.name = new_name
        book.topic = new_topic
        print("Book modified successfully.")
        return
    print("Book not found.")

  def display_books(self):
    if self.books:
      print("Available books:")
      for book in self.books:
        book.print_info()
        print()
    else:
      print("No books available.")


library = Library()

while True:
  print("\nMenu:")
  print("1. Add a book")
  print("2. Remove a book")
  print("3. Modify a book")
  print("4. Display books")
  print("5. Exit")

  choice = input("Enter your choice: ")

  if choice == '1':
    name = input("Enter the book name: ")
    topic = input("Enter the book topic: ")
    library.add_book(name, topic)

  elif choice == '2':
    name = input("Enter the book name to remove: ")
    library.remove_book(name)

  elif choice == '3':
    name = input("Enter the book name to modify: ")
    new_name = input("Enter the new name: ")
    new_topic = input("Enter the new topic: ")
    library.modify_book(name, new_name, new_topic)

  elif choice == '4':
    library.display_books()

  elif choice == '5':
    print("Goodbye!")
    break

  else:
    print("Invalid choice. Please try again.")
