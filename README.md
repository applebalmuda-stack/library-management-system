class Library:
    def __init__(self):
        self.books = []

    def add_book(self, book):
        self.books.append(book)
        print(f"'{book}' added successfully.")

    def view_books(self):
        if not self.books:
            print("No books available.")
        else:
            print("\nAvailable Books:")
            for i, book in enumerate(self.books, start=1):
                print(f"{i}. {book}")

    def search_book(self, book):
        if book in self.books:
            print(f"'{book}' is available.")
        else:
            print(f"'{book}' not found.")

    def remove_book(self, book):
        if book in self.books:
            self.books.remove(book)
            print(f"'{book}' removed successfully.")
        else:
            print(f"'{book}' not found.")


library = Library()

while True:
    print("\n===== Library Management System =====")
    print("1. Add Book")
    print("2. View Books")
    print("3. Search Book")
    print("4. Remove Book")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        book = input("Enter book name: ")
        library.add_book(book)

    elif choice == "2":
        library.view_books()

    elif choice == "3":
        book = input("Enter book name to search: ")
        library.search_book(book)

    elif choice == "4":
        book = input("Enter book name to remove: ")
        library.remove_book(book)

    elif choice == "5":
        print("Exiting Library Management System...")
        break

    else:
        print("Invalid choice. Please try again.")
