# creditcard
how the bank credit card process in python
class VisaCreditCardApplication:
    def __init__(self):
        self.applications = []
        self.application_id = 1
    
    def apply_for_visa_card(self, name, email, address):
        application_details = {
            'id': self.application_id,
            'name': name,
            'email': email,
            'address': address
        }
        self.applications.append(application_details)
        self.application_id += 1
        return application_details
    
    def get_all_applications(self):
        return self.applications


def main():
    visa_app = VisaCreditCardApplication()
    
    print("Welcome to Visa Credit Card Application System")
    while True:
        print("\n1. Apply for Visa Credit Card")
        print("2. View All Applications")
        print("3. Exit")
        
        choice = input("Enter your choice (1/2/3): ")
        
        if choice == '1':
            name = input("Enter your name: ")
            email = input("Enter your email: ")
            address = input("Enter your address: ")
            application_details = visa_app.apply_for_visa_card(name, email, address)
            print(f"\nApplication submitted successfully. Application ID: {application_details['id']}")
        
        elif choice == '2':
            applications = visa_app.get_all_applications()
            if applications:
                print("\nAll Visa Credit Card Applications:")
                for application in applications:
                    print(f"Application ID: {application['id']}, Name: {application['name']}, Email: {application['email']}, Address: {application['address']}")
            else:
                print("\nNo applications found.")
        
        elif choice == '3':
            print("Exiting the application system. Goodbye!")
            break
        
        else:
            print("Invalid choice. Please enter 1, 2, or 3.")

if __name__ == "__main__":
    main()

