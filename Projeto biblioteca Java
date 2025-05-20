package Prática;

import com.sun.jdi.Value;

import java.util.*;

public class bibliotecaComHashMap {
    public static void main(String[] args) {
        HashMap<String, ArrayList<String>> livros = new HashMap<>();
        int opcaoUsuario;
        Scanner scan = new Scanner(System.in);

        do {
            opcaoUsuario = 0;
            try {
                System.out.println("\n1) Adicionar Novo Livro" + "\n2) Pesquisar Livro por Título" +
                        "\n3) Excluir Livro pelo Título" + "\n4) Listar Todos os Livros" + "\n5) Sair do sistema");
                System.out.println("\nSelecione uma opção: ");
                opcaoUsuario = scan.nextInt();


                switch (opcaoUsuario) {
                    case 1:
                        adicionar(livros, scan);
                        break;

                    case 2:
                        pesquisa(livros, scan);
                        break;

                    case 3:
                        remover(livros, scan);
                        break;

                    case 4:
                        lista(livros, scan);
                        break;

                    case 5:
                        System.out.println("Saindo do sistema...");
                        break;

                    default:
                        System.out.println("Opção inválida, tente novamente: ");


                }
            } catch (InputMismatchException e) {
                System.out.println("Opção inválida, tente novamente...");
                scan.nextLine();
            }

        } while (opcaoUsuario != 5);

    }

    public static void adicionar(HashMap<String, ArrayList<String>> bibliotecaAdd, Scanner scan) {

        System.out.println("Digite o nome do autor: ");
        scan.nextLine();
        String autorUsuario = scan.nextLine();

        System.out.println("Digite o nome do livro: ");
        String livroUsuario = scan.nextLine();

        String chaveReal = null;

        for (String i : bibliotecaAdd.keySet()) {

            if (i.equalsIgnoreCase(autorUsuario)) {
                chaveReal = i;
                break;
            }
        }

        if (chaveReal != null) {
            if(bibliotecaAdd.equals(livroUsuario)){
                System.out.println("O livro já está registrado...");

            }else {
                bibliotecaAdd.get(chaveReal).add(livroUsuario);
                System.out.println("Livro adicionado com sucesso!!");
            }
        } else {
            ArrayList<String> novaLista = new ArrayList<>();
            novaLista.add(livroUsuario);
            bibliotecaAdd.put(autorUsuario, novaLista);
            System.out.println("Autor e Livro adicionado com sucesso!!");
        }

        /*
        for(String i : bibliotecaAdd.keySet()){
            if(bibliotecaAdd.containsKey(autorUsuario)){
                bibliotecaAdd.get(autorUsuario).add(livroUsuario);

            }else{
                ArrayList<String> novaLista = new ArrayList<>();
                bibliotecaAdd.put(autorUsuario,novaLista);
            }
        }
        */
    }

    public static void pesquisa(HashMap<String, ArrayList<String>> bibliotecaAdd, Scanner scan) {
        System.out.println("Digite o livro que você quer pesquisar: ");
        scan.nextLine();
        String livroUsuario = scan.nextLine();

        boolean encontrado = false;

        for (Map.Entry<String, ArrayList<String>> listona : bibliotecaAdd.entrySet()) {

            for (String lista : listona.getValue()) {
                if (lista.equalsIgnoreCase(livroUsuario)) {
                    System.out.println("Livro encontrado!!\n" + "Autor: " + listona.getKey() +
                            "\nLivro: " + listona.getValue());
                    encontrado = true;
                    return;
                }
            }

        }
        if (!encontrado) {
            System.out.println("Não foi possível encontrar o livro...");
        }
    }

    public static void remover(HashMap<String, ArrayList<String>> bibliotecaAdd, Scanner scan) {
        System.out.println("Digite o livro que você quer remover: ");
        scan.nextLine();
        String livroUsuario = scan.nextLine();


        boolean encontrado = false;

        for (Map.Entry<String, ArrayList<String>> listona : bibliotecaAdd.entrySet()) {

            ArrayList<String> lista = listona.getValue();
            String autor = listona.getKey();

            for (int i = 0; i < lista.size(); i++) {

                if (lista.get(i).equalsIgnoreCase(livroUsuario)) {
                    lista.remove(i);
                    System.out.println("Livro deletado com sucesso!!");
                    encontrado = true;


                    if (lista.isEmpty()) {
                        bibliotecaAdd.remove(autor);
                    }

                    break;
                }
            }

        }
            if(!encontrado){
                System.out.println("Livro não encontrado...");
            }


        }

    public static void lista(HashMap<String, ArrayList<String>> bibliotecaAdd, Scanner scan){
        for(Map.Entry<String, ArrayList<String>> listona : bibliotecaAdd.entrySet()){
            ArrayList<String> lista = listona.getValue();
            String autor = listona.getKey();

            for (int i = 0; i<lista.size();i++){
                System.out.println(autor+lista);
            }
        }
    }
}
