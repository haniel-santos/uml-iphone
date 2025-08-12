Vou criar um projeto que modela as funcionalidades do iPhone como Reprodutor Musical, Aparelho Telefônico e Navegador na Internet, seguindo os princípios de POO.

Diagrama UML (Conceitual)
text
+---------------------+
|      iPhone         |
+---------------------+
| - modelo: String    |
| - versao: String    |
+---------------------+
| + tocar()           |
| + pausar()          |
| + selecionarMusica()|
| + ligar()           |
| + atender()         |
| + iniciarCorreioVoz()|
| + exibirPagina()    |
| + adicionarNovaAba()|
| + atualizarPagina() |
+---------------------+
Implementação em Java
1. Interface ReprodutorMusical
java
public interface ReprodutorMusical {
    void tocar();
    void pausar();
    void selecionarMusica(String musica);
}
2. Interface AparelhoTelefonico
java
public interface AparelhoTelefonico {
    void ligar(String numero);
    void atender();
    void iniciarCorreioVoz();
}
3. Interface NavegadorInternet
java
public interface NavegadorInternet {
    void exibirPagina(String url);
    void adicionarNovaAba();
    void atualizarPagina();
}
4. Classe iPhone (implementa todas as interfaces)
java
public class iPhone implements ReprodutorMusical, AparelhoTelefonico, NavegadorInternet {
    private String modelo;
    private String versao;

    public iPhone(String modelo, String versao) {
        this.modelo = modelo;
        this.versao = versao;
    }

    // Implementação ReprodutorMusical
    @Override
    public void tocar() {
        System.out.println("Tocando música...");
    }

    @Override
    public void pausar() {
        System.out.println("Música pausada");
    }

    @Override
    public void selecionarMusica(String musica) {
        System.out.println("Selecionando música: " + musica);
    }

    // Implementação AparelhoTelefonico
    @Override
    public void ligar(String numero) {
        System.out.println("Ligando para: " + numero);
    }

    @Override
    public void atender() {
        System.out.println("Atendendo chamada...");
    }

    @Override
    public void iniciarCorreioVoz() {
        System.out.println("Iniciando correio de voz");
    }

    // Implementação NavegadorInternet
    @Override
    public void exibirPagina(String url) {
        System.out.println("Exibindo página: " + url);
    }

    @Override
    public void adicionarNovaAba() {
        System.out.println("Nova aba adicionada");
    }

    @Override
    public void atualizarPagina() {
        System.out.println("Página atualizada");
    }
}
5. Classe Main para teste
java
public class Main {
    public static void main(String[] args) {
        iPhone meuIphone = new iPhone("iPhone 15", "iOS 17");
        
        // Testando Reprodutor Musical
        meuIphone.tocar();
        meuIphone.pausar();
        meuIphone.selecionarMusica("Bohemian Rhapsody");
        
        // Testando Aparelho Telefônico
        meuIphone.ligar("(11) 98765-4321");
        meuIphone.atender();
        meuIphone.iniciarCorreioVoz();
        
        // Testando Navegador na Internet
        meuIphone.exibirPagina("https://www.google.com");
        meuIphone.adicionarNovaAba();
        meuIphone.atualizarPagina();
    }
}
Estrutura do Projeto no GitHub
text
iphone-java/
├── src/
│   ├── interfaces/
│   │   ├── ReprodutorMusical.java
│   │   ├── AparelhoTelefonico.java
│   │   └── NavegadorInternet.java
│   ├── iPhone.java
│   └── Main.java
├── docs/
│   └── diagrama-uml.png
└── README.md
Como Executar
Clone o repositório

Compile os arquivos Java:

text
javac src/*.java src/interfaces/*.java -d bin/
Execute a classe Main:

text
java -cp bin/ Main
