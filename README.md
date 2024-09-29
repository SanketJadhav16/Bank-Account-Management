import java.util.Scanner;

class LaxmiChitFund {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String name = null;
        String address = null;
        long mobile = 0;
        float balance = 0.0f;
        int pin = 0;

        // Infinite loop for account creation and existing user
        while (true) {
            System.out.println("********** WELCOME TO LAXMI CHIT FUND **********");
            System.out.println("**** 21 din mai paisa double ****");
            System.out.println();
            System.out.println("1. Existing user");
            System.out.println();
            System.out.println("2. Create Account");
            System.out.println();
            System.out.print("Enter an option: ");
            int option = sc.nextInt();

            switch (option) {
                case 1: {
                    // Check if user has created an account or not
                    if (name == null) {
                        System.out.println("CREATE YOUR ACCOUNT FIRST");
                        break;
                    }

                    // If user created an account, display features
                    while (true) {
                        System.out.println();
                        System.out.println("**** FEATURES ****");
                        System.out.println("1. Check Balance");
                        System.out.println("2. Deposit Amount");
                        System.out.println("3. Withdraw Amount");
                        System.out.println("4. Account Details");
                        System.out.println("5. Exit");
                        System.out.print("Enter an option: ");
                        int opt = sc.nextInt();
                        System.out.println();

                        switch (opt) {
                            case 1: {
                                System.out.println("**** Check Balance ****");
                                System.out.print("Enter your PIN: ");
                                int pin1 = sc.nextInt();
                                if (pin == pin1) {
                                    System.out.println("Account balance is: " + balance + " cr");
                                } else {
                                    System.out.println("Wrong PIN entered");
                                }
                                break;
                            }
                            case 2: {
                                System.out.println("**** Deposit Amount ****");
                                System.out.print("Enter an amount to deposit: ");
                                float deposit = sc.nextFloat();
                                balance += deposit;
                                System.out.println("Amount credited: " + deposit + " to your account.");
                                break;
                            }
                            case 3: {
                                System.out.println("**** Withdraw Amount ****");
                                System.out.print("Enter an amount to withdraw: ");
                                float withdraw = sc.nextFloat();
                                if (withdraw <= balance) {
                                    balance -= withdraw;
                                    System.out.println("Amount debited: " + withdraw + " from your account.");
                                } else {
                                    System.out.println("Insufficient Funds");
                                }
                                break;
                            }
                            case 4: {
                                System.out.println("**** Account Details ****");
                                System.out.println("Account holder name: " + name);
                                System.out.println("Address: " + address);
                                System.out.println("Mobile number: " + mobile);
                                break;
                            }
                            case 5: {
                                System.out.println("Thank you for using our application");
                                sc.close();
                                System.exit(0);
                            }
                            default: {
                                System.out.println("Wrong option entered");
                                break;
                            }
                        }
                    }
                }
                case 2: {
                    // Account details from user and storing it in variables
                    System.out.println("**** Enter your details below ****");
                    sc.nextLine(); // Consume newline
                    System.out.print("Account holder name: ");
                    name = sc.nextLine();
                    System.out.print("Address: ");
                    address = sc.nextLine();
                    System.out.print("Mobile number: ");
                    mobile = sc.nextLong();
                    System.out.print("Amount to deposit: ");
                    balance = sc.nextFloat();
                    System.out.print("PIN: ");
                    pin = sc.nextInt();
                    break;
                }
                default: {
                    // If user enters wrong options
                    System.out.println("Wrong option");
                    break;
                }
            }
            System.out.println();
        }
    }
}
# Bank-Account-Management
