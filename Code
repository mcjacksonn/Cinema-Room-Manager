import java.util.Scanner;

public class Cinema {
    public static void showSeats(String[][] seatArrangement, int numberOfRows, int numberOfSeats) {
        System.out.println("Cinema:");
        System.out.print("  ");
        for (int i = 1; i <= numberOfSeats; i++) {
            System.out.print(i + " ");
        }
        System.out.println();
        for (int i = 0; i < numberOfRows; i++) {
            System.out.print(i + 1 + " ");
            for (int j = 0; j < numberOfSeats; j++) {
                System.out.print(seatArrangement[i][j] + " ");
            }
            System.out.println();
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter the number of rows:");
        int numberOfRows = scanner.nextInt();
        System.out.println("Enter the number of seats in each row:");
        int numberOfSeats = scanner.nextInt();

        String[][] seatArrangement = new String[numberOfRows][numberOfSeats];

        for (int i = 0; i < numberOfRows; i++) {
            for (int j = 0; j < numberOfSeats; j++) {
                seatArrangement[i][j] = "S";
            }
        }

        int totalSeats = numberOfRows * numberOfSeats;
        int frontHalf = (numberOfRows / 2);
        int totalIncome;

        if (totalSeats > 60) {
            totalIncome = (frontHalf * numberOfSeats * 10) + ((numberOfRows - frontHalf) * numberOfSeats * 8);
        } else {
            totalIncome = totalSeats * 10;
        }

        int purchasedTickets = 0;
        int currentIncome = 0;

        boolean exit = false;

        while (!exit) {
            System.out.println("\n1. Show the seats");
            System.out.println("2. Buy a ticket");
            System.out.println("3. Statistics");
            System.out.println("0. Exit");
            int option = scanner.nextInt();

            switch (option) {
                case 1:
                    showSeats(seatArrangement, numberOfRows, numberOfSeats);
                    break;
                case 2:
                    while (true) {
                        System.out.println("Enter a row number:");
                        int rowNumber = scanner.nextInt();
                        System.out.println("Enter a seat number in that row:");
                        int seatNumber = scanner.nextInt();

                        if (rowNumber < 1 || rowNumber > numberOfRows || seatNumber < 1 || seatNumber > numberOfSeats) {
                            System.out.println("Wrong input!");
                        } else if (seatArrangement[rowNumber - 1][seatNumber - 1].equals("B")) {
                            System.out.println("That ticket has already been purchased!");
                        } else {
                            seatArrangement[rowNumber - 1][seatNumber - 1] = "B";
                            int ticketPrice;
                            if (totalSeats > 60) {
                                if (rowNumber <= frontHalf) {
                                    ticketPrice = 10;
                                } else {
                                    ticketPrice = 8;
                                }
                            } else {
                                ticketPrice = 10;
                            }
                            currentIncome += ticketPrice;
                            purchasedTickets++;
                            System.out.println("Ticket price: $" + ticketPrice);
                            break;
                        }
                    }
                    break;
                case 3:
                    double percentage = ((double) purchasedTickets / totalSeats) * 100;
                    System.out.println("\nNumber of purchased tickets: " + purchasedTickets);
                    System.out.printf("Percentage: %.2f%%\n", percentage);
                    System.out.println("Current income: $" + currentIncome);
                    System.out.println("Total income: $" + totalIncome);
                    break;
                case 0:
                    exit = true;
                    break;
                default:
                    break;
            }
        }
    }
}
                   
