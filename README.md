# Aula 25-11 - App Conversão de moeda

## Avaliação

* Implemente para que o usuário possa fazer conversão de outras moedas (mínimo + 3 moedas);
* Descreva abaixo o seu entendimento acerca desta atividade, explorando as funcionalidades das classes que contruímos e os principais pontos da aplicação;

## Entrega

* Clone este repositório e faça o que se pede;
* Realize um commit das suas alterações no seu repositório;
* Envie o link do repositório na avaliação gerada no classroom;

## Descritivo do Aluno:


## Funcionalidades Principais

- **Conversão de Moedas em Tempo Real:** O usuário pode escolher entre diferentes pares de moedas (como Real para Dólar, Euro para Real, etc.) e inserir um valor para conversão.
- **Integração com API Externa:** A aplicação utiliza a API AwesomeAPI para obter as cotações atualizadas das moedas.
- **Interface Simples e Intuitiva:** A interface permite que o usuário selecione a moeda de origem e destino através de botões de rádio e insira o valor a ser convertido.

## Estrutura da Aplicação

### 1. **ConversorService (Serviço)**
A API externa que fornece cotações de moeda deve ser comunicada pelo serviço `ConversorService`. Faz consultas HTTP à API usando a biblioteca `axios`.

#### Funcionalidade:
- Para recuperar cotações de moedas com base no par de moedas fornecido como parâmetro, o serviço oferece um método chamado `converterMoeda(currency: String)` que executa uma solicitação `GET`. 
- O serviço extrai os valores necessários para completar o cálculo da conversão a partir das cotações de moeda que estão incluídas na resposta da API.

#### Importância:
- O serviço facilita a manutenção e o teste de aplicações, deixando a lógica de comunicação com a API e possibilitando a conversão central da moeda.

### 2. **AppComponent (Componente Principal)**
O componente principal do programa, o `AppComponent`, é responsável por configurar a estrutura fundamental da interface do usuário. Este componente importa outros módulos e componentes necessários e serve como raiz do aplicativo.

#### Funcionalidade:
- Um componente essencial que permite o gerenciamento de rotas dentro da aplicação é o `RouterOutlet`.
- O `ConverterMoedaComponent`, responsável por supervisionar a lógica de conversão de moeda, também é importado.
- O título e o layout básico da aplicação estão contidos neste componente, que serve como ponto de partida.

### 3. **ConverterMoedaComponent (Componente de Conversão de Moeda)**
O `ConverterMoedaComponent` é o componente central onde o usuário interage diretamente com a aplicação. Ele permite que o usuário selecione o par de moedas e insira um valor para conversão.

#### Propriedades:
- `opcaoEscolhida`: Armazena o par de moedas selecionado pelo usuário.
- `valor`: O valor inserido pelo usuário para ser convertido.
- `resultado`: Exibe o valor convertido de acordo com a cotação da moeda.

#### Funcionalidade:
- Um componente essencial que permite o gerenciamento de rotas dentro da aplicação é o `RouterOutlet`.
- O `ConverterMoedaComponent`, responsável por supervisionar a lógica de conversão de moeda, também é importado.
- O título e o layout básico da aplicação estão contidos neste componente, que serve como ponto de partida.

#### Interface:
- O usuário escolhe o par de moedas (como "Real para Dólar", "Euro para Real") por meio de botões de seleção radio.
- O usuário insere o valor a ser convertido e, ao clicar no botão "Calcular", a conversão é realizada e o valor convertido é exibido em um campo de entrada desabilitado.

### 4. **Template HTML (Converter Moeda Component)**
O arquivo HTML do componente de conversão (`converter-moeda.component.html`) define a estrutura da interface do usuário para o processo de conversão de moedas.

#### Componentes da Interface:
- **Seleção de Moeda:** O usuário escolhe um par de moedas através de botões de rádio (por exemplo, "Real para Dólar", "Euro para Real").
- **Entrada de Valor:** O usuário insere o valor a ser convertido em um campo de entrada numérico.
- **Cálculo da Conversão:** Após inserir o valor, o usuário clica no botão "Calcular" para obter a conversão.
- **Exibição do Resultado:** O valor convertido é exibido em um campo de entrada desabilitado para que o usuário possa visualizá-lo sem modificá-lo.

### 5. **Testes do Componente (app.component.spec.ts)**
O arquivo de testes (`app.component.spec.ts`) contém testes unitários para o `AppComponent` e garante que a aplicação esteja funcionando corretamente.

#### Exemplos de Testes:
- **Teste 1:** Verifica se o componente `AppComponent` foi criado corretamente.
- **Teste 2:** Verifica se o título da aplicação está correto e corresponde a "conversion-app-test".
- **Teste 3:** Verifica se o título da aplicação é renderizado corretamente na interface, mostrando a mensagem esperada.

### Fluxo da Aplicação

1. O usuário acessa a interface do conversor de moedas.
2. O usuário seleciona um par de moedas (como "BRL-USD" ou "EUR-BRL") e insere um valor a ser convertido.
3. Ao clicar no botão "Calcular", o componente chama a função `calcularConversao()` que consulta o serviço `ConversorService` para obter a cotação das moedas selecionadas.
4. A cotação obtida é usada para calcular o valor convertido, que é exibido para o usuário na interface.

### Conclusão

A aplicação Angular descrita é uma ferramenta interativa e prática para conversão de moedas. Ela utiliza a API externa para fornecer cotações em tempo real, permitindo que os usuários convertam diferentes moedas de forma simples e rápida.

A estrutura do projeto é bem organizada, com a separação clara de responsabilidades entre os componentes e o serviço, o que facilita a manutenção e expansão futura da aplicação. Os testes unitários garantem que a aplicação funcione corretamente e que as funcionalidades sejam preservadas ao longo do tempo.
