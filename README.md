import java.util.Scanner;

class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        String title = "";
        String description = "";
        boolean login = false;

        // MODULE 1: ADMIN AUTHENTICATION

        System.out.println("DIGITAL NOTICE BOARD");
        System.out.println("--------------------");

        System.out.print("Enter Username: ");
        String user = sc.nextLine();

        System.out.print("Enter Password: ");
        String pass = sc.nextLine();

        if (user.equals("admin") && pass.equals("1234")) {

            login = true;
            System.out.println("Login Successful!");

            // MENU

            while (true) {

                System.out.println("\n1. Notice Creation");
                System.out.println("2. Notice Management");
                System.out.println("3. Notice Update");
                System.out.println("4. Display Notice");
                System.out.println("5. Exit");

                System.out.print("Enter Choice: ");
                int ch = sc.nextInt();
                sc.nextLine();

                // MODULE 2: NOTICE CREATION

                if (ch == 1) {

                    System.out.print("Enter Notice Title: ");
                    title = sc.nextLine();

                    System.out.print("Enter Description: ");
                    description = sc.nextLine();

                    System.out.println("Notice Created Successfully!");
                }

                // MODULE 3: NOTICE MANAGEMENT

                else if (ch == 2) {

                    System.out.println("1. View Notice");
                    System.out.println("2. Delete Notice");

                    System.out.print("Enter Choice: ");
                    int choice = sc.nextInt();
                    sc.nextLine();

                    if (choice == 1) {

                        if (title.equals("")) {
                            System.out.println("No Notice Available");
                        } else {
                            System.out.println("Title: " + title);
                            System.out.println("Description: " + description);
                        }
                    }

                    else if (choice == 2) {

                        title = "";
                        description = "";

                        System.out.println("Notice Deleted!");
                    }

                    else {
                        System.out.println("Invalid Choice");
                    }
                }

                // MODULE 4: NOTICE UPDATE

                else if (ch == 3) {

                    if (title.equals("")) {
                        System.out.println("No Notice Available");
                    } else {

                        System.out.print("Enter New Title: ");
                        title = sc.nextLine();

                        System.out.print("Enter New Description: ");
                        description = sc.nextLine();

                        System.out.println("Notice Updated Successfully!");
                    }
                }

                // DISPLAY NOTICE

                else if (ch == 4) {

                    if (title.equals("")) {
                        System.out.println("No Notice Available");
                    } else {
                        System.out.println("\nDIGITAL NOTICE BOARD");
                        System.out.println("Title: " + title);
                        System.out.println("Description: " + description);
                        System.out.println("Status: Active");
                    }
                }

                // EXIT

                else if (ch == 5) {
                    System.out.println("Thank You!");
                    break;
                }

                else {
                    System.out.println("Invalid Choice");
                }
            }

        } else {
            System.out.println("Invalid Username or Password");
        }

        sc.close();
    }
}
