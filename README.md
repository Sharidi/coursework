# coursework
git clone https://github.com/Sharidi/your-project.git
cd your-project
npm install

git push

import java.util.*;
import java.text.SimpleDateFormat;

class User {
    private String username;
    private String password;

    public User(String username, String password) {
        this.username = username;
        this.password = password;
    }

    public String getUsername() {
        return username;
    }

    public String getPassword() {
        return password;
    }
}

class CarCategory {
    private String name;
    private double dailyRate;

    public CarCategory(String name, double dailyRate) {
        this.name = name;
        this.dailyRate = dailyRate;
    }

    public String getName() {
        return name;
    }

    public double getDailyRate() {
        return dailyRate;
    }
}

class Car {
    private String vehicleNumber;
    private String brand;
    private String model;
    private int year;
    private CarCategory category;
    private boolean available;

    public Car(String vehicleNumber, String brand, String model, int year, CarCategory category) {
        this.vehicleNumber = vehicleNumber;
        this.brand = brand;
        this.model = model;
        this.year = year;
        this.category = category;
        this.available = true;
    }

    public String getVehicleNumber() {
        return vehicleNumber;
    }

    public String getBrand() {
        return brand;
    }

    public String getModel() {
        return model;
    }

    public int getYear() {
        return year;
    }

    public CarCategory getCategory() {
        return category;
    }

    public boolean isAvailable() {
        return available;
    }

    public void setAvailable(boolean available) {
        this.available = available;
    }
}

class Customer {
    private int customerId;
    private String name;
    private String email;
    private String phone;

    public Customer(int customerId, String name, String email, String phone) {
        this.customerId = customerId;
        this.name = name;
        this.email = email;
        this.phone = phone;
    }

    public int getCustomerId() {
        return customerId;
    }

    public String getName() {
        return name;
    }

    public String getEmail() {
        return email;
    }

    public String getPhone() {
        return phone;
    }
}

class RentalTransaction {
    private int transactionId;
    private Customer customer;
    private Car car;
    private int rentalDays;
    private double totalCost;
    private Date startDate;
    private boolean returned;

    public RentalTransaction(int transactionId, Customer customer, Car car, int rentalDays, Date startDate) {
        this.transactionId = transactionId;
        this.customer = customer;
        this.car = car;
        this.rentalDays = rentalDays;
        this.startDate = startDate;
        this.totalCost = rentalDays * car.getCategory().getDailyRate();
        this.returned = false;
    }

    public int getTransactionId() {
        return transactionId;
    }

    public Customer getCustomer() {
        return customer;
    }

    public Car getCar() {
        return car;
    }

    public int getRentalDays() {
        return rentalDays;
    }

    public double getTotalCost() {
        return totalCost;
    }

    public Date getStartDate() {
        return startDate;
    }

    public boolean isReturned() {
        return returned;
    }

    public void setReturned(boolean returned) {
        this.returned = returned;
    }
}

public class CarRentalApp {
    private static Scanner scanner = new Scanner(System.in);
    private static Map<String, User> users = new HashMap<>();
    private static Map<String, CarCategory> carCategories = new HashMap<>();
    private static Map<String, Car> cars = new HashMap<>();
    private static Map<Integer, Customer> customers = new HashMap<>();
    private static Map<Integer, RentalTransaction> rentalTransactions = new HashMap<>();
    private static int transactionIdCounter = 1;

    public static void main(String[] args) {
        // Create default admin user
        users.put("admin", new User("admin", "password"));

        while (true) {
            System.out.println("Car Rental System");
            System.out.println("1. Login");
            System.out.println("2. Exit");
            System.out.print("Enter your choice: ");
            int choice = scanner.nextInt();
            scanner.nextLine(); // Consume newline

            switch (choice) {
                case 1:
                    login();
                    break;
                case 2:
                    System.out.println("Exiting the application.");
                    System.exit(0);
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
    }

    private static void login() {
        System.out.print("Username: ");
        String username = scanner.nextLine();
        System.out.print("Password: ");
        String password = scanner.nextLine();

        User user = users.get(username);
        if (user != null && user.getPassword().equals(password)) {
            System.out.println("Login successful!");
            mainMenu();
        } else {
            System.out.println("Login failed. Invalid username or password.");
        }
    }

    private static void mainMenu() {
        while (true) {
            System.out.println("Main Menu");
            System.out.println("1. Manage Car Categories");
            System.out.println("2. Manage Cars");
            System.out.println("3. Manage Customers");
            System.out.println("4. List all Rentals");
            System.out.println("5. New Rent");
            System.out.println("6. Car Return");
            System.out.println("7. Display Overdue Rentals");
            System.out.println("8. Logout");
            System.out.print("Enter your choice: ");

            int choice = scanner.nextInt();
            scanner.nextLine(); // Consume newline

            switch (choice) {
                case 1:
                    manageCarCategories();
                    break;
                case 2:
                    manageCars();
                    break;
                case 3:
                    manageCustomers();
                    break;
                case 4:
                    listAllRentals();
                    break;
                case 5:
                    newRent();
                    break;
                case 6:
                    carReturn();
                    break;
                case 7:
                    displayOverdueRentals();
                    break;
                case 8:
                    System.out.println("Logging out.");
                    return;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
    }

    private static void manageCarCategories() {
        // Implement CRUD operations for car categories
    }

    private static void manageCars() {
        // Implement CRUD operations for cars
    }

    private static void manageCustomers() {
        // Implement CRUD operations for customers
    }

    private static void listAllRentals() {
        // List all rental transactions
    }

    private static void newRent() {
        // Implement the process for creating a new rental transaction
    }

    private static void carReturn() {
        // Implement the car return process
    }

    private static void displayOverdueRentals() {
        // Display all overdue rentals
    }
}
