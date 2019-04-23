import java.util.Scanner;

public class Foothill
{
   public static void main(String[] args)
   {
      String menu, free, amount;
      final int FREE_STAMPS = 7;
      char process = '\u0000';
      int yogurts = 0;
      int stamps = 0;
      boolean flag = false;
      boolean check1 = false;
      boolean check2 = false;
      boolean check3 = false;
      Scanner input = new Scanner(System.in);

      // main loop that holds all of the other loops
      while(!flag)
      {
         // loops until valid menu input is entered
         while (!check1)
         {
            System.out.println("Menu:");
            System.out.println("   P (Process Purchase)");
            System.out.println("   S (Shut Down)");
            System.out.println("What would you like to do?");
            menu = input.nextLine();
            menu = menu.toLowerCase();

            // checks if input is valid
            if (menu.charAt(0) == 's' || menu.charAt(0) == 'p')
            {
               process = menu.charAt(0);
               check1 = true;
            }
            else
            {
               System.out.println("Please enter a valid value." + "\n");
            }
         } 
         // checks if the input is s to shut down
         if (process == 's')
         {
            System.out.println("Shutting Down...");
            System.exit(0);
         }
         // loops until valid input is entered
         while (!check2)
         {
            // user qualifies for a free yogurt prompt
            if (stamps >= FREE_STAMPS)
            {
               System.out.println("You have " + stamps + " stamps"
                     + " would you like to use them? (y or n)");
               free = input.nextLine();
               free = free.toLowerCase();

               // checks if there is a valid input
               if (free.charAt(0) == 'y' || free.charAt(0) == 'n')
               {
                  process = free.charAt(0);
                  check2 = true;
               }
               else
               {
                  System.out.println("Please enter a valid value.");
               }
            }
            else
            {
               check2 = true;
            }
         }
         // rewards with one free yogurt
         if (process == 'y')
         {
            stamps -= FREE_STAMPS;
            System.out.println("You now have " + stamps + " stamps.");
            System.out.println("Enjoy your free yogurt!" + "\n");
            check3 = true;
         }            
         // loops until a valid number is entered
         while (!check3)
         {
            System.out.println("How many yogurts would you like?");    
            amount = input.nextLine();
            
            // checks validity and rewards stamps
            if (Integer.parseInt(amount) >= 1)
            {
               yogurts = Integer.parseInt(amount);
               stamps += yogurts;
               System.out.println("Enjoy your yogurt.");
               System.out.println("You now have " + stamps +
                     " stamps." + "\n");
               check3 = true;
            }
            else 
            {
               System.out.println("Please enter a valid number.");
            }
         }
         // changes all checks to default to re-run the main loop
         flag = false;
         check1 = false;
         check2 = false;
         check3 = false;
      }
      input.close();
   }  
}


/*
 \\\\\\\\\\\\\\\ PASTED OUTPUT //////////////////
 
 ----------------RUN 1-------------------------
Menu:
 
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
L
Please enter a valid value.

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
0
Please enter a valid value.

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
P
How many yogurts would you like?
3
Enjoy your yogurt.
You now have 3 stamps.

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
pass
How many yogurts would you like?
0
Please enter a valid number.
How many yogurts would you like?
4
Enjoy your yogurt.
You now have 7 stamps.

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
PASS
You have 7 stamps would you like to use them? (y or n)
10
Please enter a valid value.
You have 7 stamps would you like to use them? (y or n)
hello
Please enter a valid value.
You have 7 stamps would you like to use them? (y or n)
Nope
How many yogurts would you like?
10
Enjoy your yogurt.
You now have 17 stamps.

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
p34095
You have 17 stamps would you like to use them? (y or n)
nOO
How many yogurts would you like?
3
Enjoy your yogurt.
You now have 20 stamps.

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
PASSSS
You have 20 stamps would you like to use them? (y or n)
03
Please enter a valid value.
You have 20 stamps would you like to use them? (y or n)
YES
You now have 13 stamps.
Enjoy your free yogurt!

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
P
You have 13 stamps would you like to use them? (y or n)
ya
You now have 6 stamps.
Enjoy your free yogurt!

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
s
Shutting Down...
---------------------------------------------------------
---------------RUN 2-------------------------------
Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
Q
Please enter a valid value.

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
qwerty
Please enter a valid value.

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
10eiP
Please enter a valid value.

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
Pass
How many yogurts would you like?
20
Enjoy your yogurt.
You now have 20 stamps.

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
NOS
Please enter a valid value.

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
p
You have 20 stamps would you like to use them? (y or n)
10
Please enter a valid value.
You have 20 stamps would you like to use them? (y or n)
Genius
Please enter a valid value.
You have 20 stamps would you like to use them? (y or n)
grey10293
Please enter a valid value.
You have 20 stamps would you like to use them? (y or n)
Yessir
You now have 13 stamps.
Enjoy your free yogurt!

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
party
You have 13 stamps would you like to use them? (y or n)
NO4987239481
How many yogurts would you like?
0
Please enter a valid number.
How many yogurts would you like?
10
Enjoy your yogurt.
You now have 23 stamps.

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
PAR
You have 23 stamps would you like to use them? (y or n)
YEEET
You now have 16 stamps.
Enjoy your free yogurt!

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
109pos
Please enter a valid value.

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
pos
You have 16 stamps would you like to use them? (y or n)
NAH
How many yogurts would you like?
1
Enjoy your yogurt.
You now have 17 stamps.

Menu:
   P (Process Purchase)
   S (Shut Down)
What would you like to do?
SHUT DOWN
Shutting Down...
*/