# Caesar
package com.company;
import java.util.Scanner;
public class Main {



        public static void main(String[] args) {
            // write your code here
            Scanner input  = new Scanner(System.in);


            int k;
            String mytext = "";

            do {
                System.out.print("Rotation: ");
                k = input.nextInt();
            } while (k < 0 || k > 26);

            do {
                System.out.println("Success");
                System.out.print("Plain text: ");

                mytext = input.nextLine();
            } while (mytext.equals(""));

            String message = mytext;
            if (k > 0 && k < 25)
            {
                message = encode(mytext.toLowerCase(),k);
                System.out.println(message);

            }
        }

        static String encode(String ciphertext, int k ) {

            String message = "";
            int q;

            for (int i = 0; i < ciphertext.length(); i++) {
                q = ciphertext.charAt(i);
                if (Character.isUpperCase(q)){
                    char finaltext = (char) q;
                    message += finaltext;
                } else if (Character.isSpaceChar(q)){
                    message += " ";
                }

                else {
                    int letnum = q + k;
                    if (Character.isLowerCase(q)) {
                        letnum = (letnum - 97) % 26 + 97;
                    }

                    char finaltext = (char) letnum;
                    message += finaltext;

                }
            }




                return message;
            }
        }
