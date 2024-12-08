#  // Print Bill
                Console.WriteLine();
                Console.WriteLine("--------------------------------------------");
                Console.WriteLine("------------------- BILL -------------------");
                Console.WriteLine("--------------------------------------------");
                Console.WriteLine("Customer Name: {0}", customer.Name);
                Console.WriteLine("Number Of Coffee Bags: {0}", numCoffeeBags);
                Console.WriteLine("Total Cost Of Bags: {0:C}", totalCost);
                Console.WriteLine("Discount: {0:C}", discount);
                Console.WriteLine("--------------------------------------------");
                Console.WriteLine("Amount Payable: {0:C}", totalCost - discount);
                Console.WriteLine("--------------------------------------------");

                // Input User Choice to continue or exit
                Console.Write("Input Y/y To Continue Or Any Other Key To Exit: ");
                choice = Console.ReadLine().ToLower()[0];
                Console.WriteLine();
            } while (choice == 'y');

            // Optionally display all orders stored
            Console.WriteLine("All Orders Processed:");
            foreach (var order in orders)
            {
                Console.WriteLine($"Customer: {order.CustomerName}, Bags: {order.NumCoffeeBags}, Total: {order.TotalCost:C}, Discount: {order.Discount:C}, Payable: {order.TotalCost - order.Discount:C}");
            }
        }
    }

    // Customer class to store customer information
    class Customer
    {
        public string Name { get; set; }
        public bool IsReseller { get; set; }
    }

    // CustomerOrder class to store order details
    class CustomerOrder
    {
        public string CustomerName { get; set; }
        public int NumCoffeeBags { get; set; }
        public double TotalCost { get; set; }
        public double Discount { get; set; }
    }
}
