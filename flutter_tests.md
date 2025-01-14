# Rotina de Testes no Flutter 📲

Este documento descreve as diretrizes e a rotina para implementação de testes em projetos Flutter, com base nos princípios da Pirâmide de Testes. O objetivo é garantir qualidade, eficiência e manutenibilidade no desenvolvimento.

[Documentação Oficial de Testes](https://docs.flutter.dev/testing)

<br />
 
## 📋 Pirâmide de Testes
A Pirâmide de Testes é um conceito que organiza os testes de software em três níveis principais:

##### 1. **Testes Unitários** 
Testes que verificam a menor unidade funcional do código, como classes, métodos ou funções isoladas.
 
##### 2. **Testes de Widget**
Testes que avaliam widgets individuais ou pequenas partes da interface do usuário em isolamento.

##### 3. **Testes de Integração**
Testes que validam o funcionamento completo do sistema, verificando a interação entre diferentes partes do aplicativo.

<p align="center">
  <img src="https://miro.medium.com/v2/resize:fit:1400/1*ho3TNCRaLEAVYyiFsSXOLA.jpeg" alt="Piramide" width="400" height="320">
</p>

<br />

## 📌 Estrutura de Pastas
Organize os testes no projeto seguindo esta estrutura:

```bash
test/
├── unit/
├── widget/
└── integration/
```

<br />

## 🛠 Configurações
Certifique-se de que o projeto está configurado para testes:

Lembre-se que o pacote de testes deve estar sempre vinculado ao seu ``pubspec.yaml`` (já incluído em projetos Flutter por padrão):

```bash
dev_dependencies:
  flutter_test:
    sdk: flutter
```
<br />

## 🌌 Arrange, Act, Assert (AAA) em Testes Flutter
O padrão Arrange, Act, Assert é uma metodologia amplamente utilizada para estruturar casos de teste de forma clara e organizada. Ele divide o teste em três fases principais:
- **Arrange (Preparar)** : Configure as condições iniciais, variáveis ou dados necessários para o teste. Aqui você prepara tudo que será usado na execução do teste.
Exemplo: Inicializar variáveis ou mockar dependências.
- **Act (Agir)** : Execute a ação que será testada. É o momento de chamar a função ou método que está sendo avaliado.
*Exemplo*: Chamar a função que realiza a soma de dois números.
- **Assert (Verificar)** : Valide o resultado da ação realizada. Aqui, você verifica se o comportamento ou o resultado está de acordo com o esperado.
Exemplo: Comparar o valor retornado com o valor esperado usando o método expect.

### Exemplo no Flutter:

```bash
 test("Verificar soma de dois números", () {
   // Arrange (Preparar)
   var a = 200;
   var b = 11;
 
   // Act (Agir)
   var soma = add(a, b);
 
   // Assert (Verificar)
   expect(soma, 211);
 });
```

<br />

## 🧪 Testes Unitários
- **Objetivo** : Garantir que métodos e classes individuais funcionem corretamente.
- **Cobertura** : Lógica de negócios, validações, cálculos e outros componentes isolados.
- **Ferramentas** : Utilize o pacote padrão flutter_test ou bibliotecas como mockito para simulação.

### Exemplo de Teste Unitário:

```bash
import 'package:flutter_test/flutter_test.dart';
import 'package:meu_app/calculadora.dart';

void main() {
  group('Teste da Calculadora', () {
    test('Deve somar dois números corretamente', () {
      final calculadora = Calculadora();
      expect(calculadora.somar(2, 3), 5);
    });
  });
}
```

<br />

## 🖼️ Testes de Widget
- **Objetivo** : Verificar a aparência e o comportamento de widgets individuais.
- **Cobertura** : Componentes da interface, interações básicas (toques, gestos).

### Exemplo de Teste de Widget:

```bash
import 'package:flutter_test/flutter_test.dart';
import 'package:meu_app/widgets/meu_botao.dart';

void main() {
  testWidgets('Deve exibir o texto correto no botão', (WidgetTester tester) async {
    await tester.pumpWidget(const MeuBotao(texto: 'Clique aqui'));
    expect(find.text('Clique aqui'), findsOneWidget);
  });
}
```

<br />

## 🔗 Testes de Integração
- **Objetivo** : Garantir que diferentes partes do aplicativo funcionem bem juntas.
- **Cobertura** : Fluxos de usuário, navegação e interações completas.
- **Ferramentas** : Use o comando ``flutter drive`` com suporte ao ``integration_test``.

### Exemplo de Teste de Integração:

```bash
import 'package:flutter_test/flutter_test.dart';
import 'package:integration_test/integration_test.dart';
import 'package:meu_app/main.dart';

void main() {
  IntegrationTestWidgetsFlutterBinding.ensureInitialized();

  testWidgets('Teste de fluxo de login', (WidgetTester tester) async {
    await tester.pumpWidget(const MyApp());
    await tester.enterText(find.byKey(const Key('campo_email')), 'teste@email.com');
    await tester.enterText(find.byKey(const Key('campo_senha')), '123456');
    await tester.tap(find.byKey(const Key('botao_login')));
    await tester.pumpAndSettle();

    expect(find.text('Bem-vindo!'), findsOneWidget);
  });
}

```

<br />

## 💡 Boas Práticas
- **Priorize Testes Unitários** : Eles são mais rápidos, fáceis de manter e cobrem a maior parte do código.
- **Mock Dependências** : Para testes unitários e de widgets, isole dependências externas como APIs e bancos de dados.
- **Mantenha a Simplicidade** : Evite testes desnecessariamente complexos ou dependentes de configurações específicas.

<br />

## 🚀 Execução dos Testes

- Executar todos os testes:
```bash
flutter test
```

- Executar testes de integração:
```bash
flutter drive --target=test_driver/app.dart
```


## 
Seguindo esta rotina, conseguimos manter um aplicativo estável, com alta cobertura de testes e uma base de código confiável. 🛡️

<br />

<img src="https://transparencia.sebrae.com.br/static/media/slogo-azul.97b61ad7.png" alt="Profile Image" width="280" height="150">
