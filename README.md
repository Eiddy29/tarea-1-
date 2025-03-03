Trabajo de calculadora 

public class CalculadoraAvanzada {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int opcion;
        
        do {
            System.out.println("=== Calculadora Científica en Java ===");
            System.out.println("1. Seno");
            System.out.println("2. Coseno");
            System.out.println("3. Tangente");
            System.out.println("4. Logaritmo en base 10");
            System.out.println("5. Logaritmo natural (ln)");
            System.out.println("6. Valor absoluto");
            System.out.println("7. Salir");
            System.out.print("Seleccione una opción: ");
            
            opcion = scanner.nextInt();
            
            if (opcion >= 1 && opcion <= 6) {
                System.out.print("Ingrese un número: ");
                double numero = scanner.nextDouble();
                double resultado = 0;
                
                switch (opcion) {
                    case 1:
                        resultado = Math.sin(Math.toRadians(numero)); // Convierte grados a radianes
                        System.out.println("Seno de " + numero + "° = " + resultado);
                        break;
                    case 2:
                        resultado = Math.cos(Math.toRadians(numero));
                        System.out.println("Coseno de " + numero + "° = " + resultado);
                        break;
                    case 3:
                        resultado = Math.tan(Math.toRadians(numero));
                        System.out.println("Tangente de " + numero + "° = " + resultado);
                        break;
                    case 4:
                        if (numero > 0) {
                            resultado = Math.log10(numero);
                            System.out.println("Logaritmo base 10 de " + numero + " = " + resultado);
                        } else {
                            System.out.println("El logaritmo base 10 no está definido para números ≤ 0");
                        }
                        break;
                    case 5:
                        if (numero > 0) {
                            resultado = Math.log(numero); // logaritmo natural (base e)
                            System.out.println("Logaritmo natural (ln) de " + numero + " = " + resultado);
                        } else {
                            System.out.println("El logaritmo natural no está definido para números ≤ 0");
                        }
                        break;
                    case 6:
                        resultado = Math.abs(numero);
                        System.out.println("Valor absoluto de " + numero + " = " + resultado);
                        break;
                }
            } else if (opcion != 7) {
                System.out.println("Opción no válida. Intente nuevamente.");
            }
            
            System.out.println();
        } while (opcion != 7);

        System.out.println("Calculadora finalizada.");
        scanner.close();
    }
}
