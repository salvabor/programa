# programa
creado con hilos

import java.util.Scanner;
import javax.swing.JOptionPane;

public class resolucionProblemas {

    static double xa = 0, xb, eva1 = 0, eva2 = 0, formula = 0, eva3 = 0, conta = 0, a = 0;

    double e = 2.7181828;

    Scanner sc = new Scanner(System.in);

    public void pedirDatos() {

        if (conta == 0) {
            System.out.println("Daame el numero1 ");
            xa = sc.nextDouble();
            System.out.println("Daame el numero 2");
            xb = sc.nextDouble();
            conta = 1;
        }

        formula();
   
        if (eva1 > 0 && eva2 > 0) {
            System.out.println(" Dame Otros valores ");
              System.exit(0);
        } else  {
            while (a < 23) {
                ciclo();
                a = a + 1;
           

            }

        }

    }

    public void ciclo() {
        formula2();
        
        mostrardatos();
        comprobacion1();
        formula2();
             System.out.println(" " + formula+"   "+eva1+"   "+ eva2);
        mostrardatos();
   

    }

    public void mostrardatos() {

        if (xa < xb) {
            System.out.println("    " + xa + "          " + xb + "  \n");

        } else if (xb <= xa) {
            System.out.println("    " + xb + "          " + xa + "  \n");
        }

    }

    public void formula() {
        double a = Math.pow(e, -xa);
        double x = Math.log(xa);
        eva1 = a - x;

        double a2 = Math.pow(e, -xb);
        double x2 = Math.log(xb);
        eva2 = a2 - x2;

    }

    public void comprobacion1() {
        double aux2 = 0;
        double a2 = Math.pow(e, -xb);
        double x2 = Math.log(xb);
        aux2 = a2 - x2;

        double aux = 0;
        double a = Math.pow(e, -xa);
        double x = Math.log(xa);
        aux = a - x;

        verificarumero(aux, aux2);

    }

    public void verificarumero(double aux, double aux2) {
      
        if (eva3 <= 0) {

            if (eva3 > aux2) {

                if (formula < xb) {
                    xb = formula;

                }
            }

            if (eva3 > aux) {

                if (formula < xa) {
                    xa = formula;

                }
            }
        }

        if (eva3 >= 0) {

            if (eva3 < aux2) {

                if (formula < xb) {
                    xb = formula;

                }
            }

            if (eva3 < aux) {

                if (formula < xa) {
                    xa = formula;
                
                }
            }
        }
        
    
        
           


    }

    public void formula2() {

        formula = (xa + xb) / 2;

        double a = Math.pow(e, -formula);
        double x = Math.log(formula);
        eva3 = a - x;

    }

    public static void main(String arg[]) {
        resolucionProblemas r = new resolucionProblemas();
        r.pedirDatos();

    }

}
