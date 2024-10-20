# Calculadora de Gorjetas

=======
# 1. Importação de pacotes:
    " import 'package:flutter/material.dart';"

O pacote flutter/material.dart é importado para usar componentes visuais e a estrutura de design Material Design.

# 2. Função principal:
    " void main() {runApp(const HomePage());}"

a função main inicia a execução do aplicativo. Ela utiliza a função runApp() para rodar o widget raiz, que neste caso é HomePage.

# 3. Classe HomePage:
    "class HomePage extends StatelessWidget {
    const HomePage({super.key});

    @override
    Widget build(BuildContext context) {
        return const MaterialApp(
        home: ScaffoldHome(),
        );
    }
    }"

A classe HomePage é um StatelessWidget. Ela define o widget de nível mais alto que será exibido, e retorna um MaterialApp que especifica o widget ScaffoldHome como sua home.

# 4. Classe ScaffoldHome:
    "class ScaffoldHome extends StatelessWidget {
    const ScaffoldHome({super.key});

    @override
    Widget build(BuildContext context) {
        return Scaffold(
        appBar: AppBar(
            title: const Text(
            "Calcula Gorjetas",
            style: TextStyle(color: Colors.white, fontWeight: FontWeight.bold),
            ),
            backgroundColor: Colors.blueGrey.shade400,
            centerTitle: true,
        ),
        backgroundColor: Colors.blue.shade50,
        body: const HomeBody(),
        );
    }
    }"

ScaffoldHome é um widget que estrutura a tela do app, utilizando o widget Scaffold do Flutter para fornecer uma barra de app (AppBar), um corpo principal (body), e outras propriedades como cor de fundo.

    - AppBar: Tem o título "Calcular Gorjetas" e um estilo personalizado;
    - Cor de fundo: é configurada de acordo como o desenvolvedor preferir;
    - Corpo (body): é definido como o widget HomeBody;

# 5. Classe HomeBody e o seu estado:

A classe HomeBody será um StatefulWidget, pois, o valor que será exbido, ou seja, o valor da gorjeta que foi calculado, será alterado conforme o usuário interage com o app.

    "class HomeBody extends StatefulWidget {
    "  const HomeBody({super.key});

    @override
    State<HomeBody> createState() => _HomeBodyState();
    }"

é valido ressaltar que a função createState() cria uma instância de _HomeBodyState, que gerencia o estado da calculadora.

# 6. Classe _HomeBodyState:

    "class _HomeBodyState extends State<HomeBody> {
    late double _resultado;
    late TextEditingController _textEditingController;"

- _resultado: vai armazenar o valor calculado da conta mais o valor da gorjeta.
- _textEditingController: vai controlar o texto inserido pelo usuário no campo de entrada.

    " @override
     void initState() {
     _resultado = 0;
     _textEditingController = TextEditingController();
     super.initState();
     } "

O método "initState()" vai inicializar o estado da classe. Aqui, "_resultado" será definido inicialmente como 0, e o "_textEditingController" será criado para controlar o valor do campo de texto.

# 7. Função calcula()

     "void calcula() {
    setState(() {
        _resultado = double.parse(_textEditingController.value.text) * 1.1;
    });
    }" 

A função calcula() vai ler o valor da conta e multiplicar por 1.1 (10% da gorjeta) e atualizar o "_resultado". A função "setState()" será chamada para garantir que a interface seja atualizada quando o valor de "_resultado" mudar.

# 8. Construção do widget principal:

    - Container: vai exibir uma imagem circular (ícone que será utilizado no app), mas pode ter outros shapes caso preferir.
    - TextField: será o campo de texto para o usuário inserir o valor da conta. Quando o valor da conta é alterado, a função "calcula()" será chamada de forma automática.
    - KeyboardType: está sendo configurado para aceitar apenas números.
    - Texto do Resultado: irá exibir o valor total (conta + gorjeta), sendo formatado para utilizar duas casas decimais.
>>>>>>> 542e1bb (App de calculadora de gorjetas)
