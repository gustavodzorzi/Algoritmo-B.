## 1. Contar quantas vezes uma letra aparece em uma palavra
import java.util.Scanner;

public class Exercicio1 {

    public static void contarLetra(String palavra, char letra) {
        int contador = 0;

        for (int i = 0; i < palavra.length(); i++) {
            if (palavra.charAt(i) == letra) {
                contador++;
            }
        }

        System.out.println("A letra aparece " + contador + " vez(es).");
    }

    public static void main(String[] args) {

        Scanner teclado = new Scanner(System.in);

        System.out.print("Digite uma palavra: ");
        String palavra = teclado.nextLine();

        System.out.print("Digite uma letra: ");
        char letra = teclado.next().charAt(0);

        contarLetra(palavra, letra);

        teclado.close();
    }
}

##2. Verificar se uma data é válida
import java.util.Scanner;

public class Exercicio2 {

    public static void verificarData(String dia, String mes, String ano) {

        int d = Integer.parseInt(dia);
        int m = Integer.parseInt(mes);
        int a = Integer.parseInt(ano);

        boolean valida = true;

        if (m < 1 || m > 12) {
            valida = false;
        }

        if (d < 1 || d > 31) {
            valida = false;
        }

        if (m == 2 && d > 29) {
            valida = false;
        }

        if ((m == 4 || m == 6 || m == 9 || m == 11) && d > 30) {
            valida = false;
        }

        if (m == 2 && d == 29) {
            if (!((a % 400 == 0) || (a % 4 == 0 && a % 100 != 0))) {
                valida = false;
            }
        }

        if (valida) {
            System.out.println("DATA VÁLIDA");
        } else {
            System.out.println("DATA INVÁLIDA");
        }
    }

    public static void main(String[] args) {

        Scanner teclado = new Scanner(System.in);

        System.out.print("Digite o dia: ");
        String dia = teclado.nextLine();

        System.out.print("Digite o mês: ");
        String mes = teclado.nextLine();

        System.out.print("Digite o ano: ");
        String ano = teclado.nextLine();

        verificarData(dia, mes, ano);

        teclado.close();
    }
}
##3. Contar a quantidade de vogais de uma frase
import java.util.Scanner;

public class Exercicio3 {

    public static int contarVogais(String frase) {

        int contador = 0;

        for (int i = 0; i < frase.length(); i++) {

            char letra = frase.charAt(i);

            if (letra == 'a' || letra == 'e' || letra == 'i'
                    || letra == 'o' || letra == 'u'
                    || letra == 'A' || letra == 'E' || letra == 'I'
                    || letra == 'O' || letra == 'U') {

                contador++;
            }
        }

        return contador;
    }

    public static void main(String[] args) {

        Scanner teclado = new Scanner(System.in);

        System.out.print("Digite uma frase: ");
        String frase = teclado.nextLine();

        int resultado = contarVogais(frase);

        System.out.println("Quantidade de vogais: " + resultado);

        teclado.close();
    }
}
##4. Retornar uma frase totalmente em maiúscula
import java.util.Scanner;

public class Exercicio4 {

    public static String deixarMaiuscula(String frase) {

        return frase.toUpperCase();
    }

    public static void main(String[] args) {

        Scanner teclado = new Scanner(System.in);

        System.out.print("Digite uma frase: ");
        String frase = teclado.nextLine();

        String resultado = deixarMaiuscula(frase);

        System.out.println("Frase em maiúscula: " + resultado);

        teclado.close();
    }
}
##5. Verificar se um vetor está ordenado
import java.util.Scanner;

public class Exercicio5 {

    public static boolean estaOrdenado(int[] vetor, int tamanho) {

        for (int i = 0; i < tamanho - 1; i++) {

            if (vetor[i] > vetor[i + 1]) {
                return false;
            }
        }

        return true;
    }

    public static void main(String[] args) {

        Scanner teclado = new Scanner(System.in);

        System.out.print("Digite o tamanho do vetor: ");
        int tamanho = teclado.nextInt();

        int[] vetor = new int[tamanho];

        for (int i = 0; i < tamanho; i++) {

            System.out.print("Digite o número " + (i + 1) + ": ");
            vetor[i] = teclado.nextInt();
        }

        boolean resultado = estaOrdenado(vetor, tamanho);

        System.out.println("Resultado: " + resultado);

        teclado.close();
    }
}
##6. Retornar o primeiro nome de um nome completo
import java.util.Scanner;

public class Exercicio6 {

    public static String primeiroNome(String nomeCompleto) {

        int posicao = nomeCompleto.indexOf(" ");

        return nomeCompleto.substring(0, posicao);
    }

    public static void main(String[] args) {

        Scanner teclado = new Scanner(System.in);

        System.out.print("Digite seu nome completo: ");
        String nome = teclado.nextLine();

        String primeiro = primeiroNome(nome);

        System.out.println("Primeiro nome: " + primeiro);

        teclado.close();
    }
}


