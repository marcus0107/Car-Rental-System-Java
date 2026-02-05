import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);
        RentalAgency agency = new RentalAgency();

        // Sample Data (Test Cases)
        agency.addCar(new Car("C1", "Toyota Corolla"));
        agency.addCar(new Car("C2", "Honda Civic"));

        agency.addCustomer(new Customer("U1", "Chris"));
        agency.addCustomer(new Customer("U2", "Taylor"));

        int choice;

        do {
            System.out.println("\n===== CAR RENTAL SYSTEM =====");
            System.out.println("1. Show Cars");
            System.out.println("2. Rent Car");
            System.out.println("3. Return Car");
            System.out.println("4. Exit");
            System.out.print("Choose option: ");

            choice = input.nextInt();
            input.nextLine();

            switch(choice) {

                case 1:
                    agency.showAllCars();
                    break;

                case 2:
                    System.out.print("Enter Car ID: ");
                    String carId = input.nextLine();

                    System.out.print("Enter Customer ID: ");
                    String custId = input.nextLine();

                    agency.rentCar(carId, custId);
                    break;

                case 3:
                    System.out.print("Enter Car ID to return: ");
                    agency.returnCar(input.nextLine());
                    break;

                case 4:
                    System.out.println("Exiting system...");
                    break;

                default:
                    System.out.println("Invalid option.");
            }

        } while(choice != 4);

        input.close();
    }
}
