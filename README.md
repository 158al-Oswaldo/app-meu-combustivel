# Meu Combustível

Aplicativo Android desenvolvido em **C# com .NET MAUI**, destinado a comparar os preços da gasolina e do etanol e identificar qual combustível apresenta o melhor custo-benefício.

O projeto foi desenvolvido como atividade acadêmica do curso técnico em Desenvolvimento de Sistemas da **Etec de Cubatão**, com o objetivo de praticar o desenvolvimento de interfaces gráficas, a manipulação de dados e a implementação de lógica de programação para dispositivos móveis.

## Funcionalidades

- Cadastro da marca do veículo.
- Cadastro do modelo do veículo.
- Entrada do preço da gasolina por litro.
- Entrada do preço do etanol por litro.
- Comparação automática dos preços.
- Exibição de uma recomendação personalizada com a marca e o modelo do veículo.

## Regra de cálculo

O aplicativo utiliza a regra dos 70% para comparar os combustíveis.

**Fórmula:**

```text
Preço do etanol ≤ Preço da gasolina × 0,70
```

Quando o preço do etanol é menor ou igual a 70% do preço da gasolina, o aplicativo recomenda o etanol. Caso contrário, recomenda a gasolina.

Essa é uma regra prática simplificada; o resultado real depende do consumo específico de cada veículo.

### Exemplo

| Informação | Valor |
|---|---|
| Marca | Chevrolet |
| Modelo | Opala Diplomata |
| Gasolina | R$ 6,29 |
| Etanol | R$ 3,99 |

**Resultado:**

> O etanol está compensando para o seu Hyundai Tucson.

## Tecnologias utilizadas

| Tecnologia | Finalidade |
|---|---|
| C# | Lógica de programação |
| .NET 10 | Plataforma de desenvolvimento |
| .NET MAUI | Desenvolvimento de aplicações multiplataforma |
| XAML | Construção da interface gráfica |
| Android SDK | Compilação para Android |
| Java JDK 21 | Ferramentas necessárias à compilação Android |
| Fedora Linux | Ambiente de desenvolvimento |

### Arquivos principais

**MainPage.xaml:** define a interface gráfica do aplicativo, incluindo os campos de entrada e o botão de comparação.

**MainPage.xaml.cs:** implementa a lógica de cálculo e a apresentação do resultado ao usuário.

**MauiProgram.cs:** configura e inicializa os serviços do .NET MAUI.

## Compilação no Fedora Linux

Embora o .NET MAUI seja normalmente desenvolvido com o Visual Studio no Windows, este projeto foi compilado para Android utilizando o Fedora Linux.

### Pré-requisitos

- .NET SDK 10
- Workload `maui-android`
- Android SDK
- JDK 21
- Dispositivo Android ou emulador para testes

### Compilar o projeto

```bash
dotnet build -f net10.0-android \
  -p:AndroidSdkDirectory="$HOME/Android/Sdk" \
  -p:JavaSdkDirectory="$JAVA_HOME"
```

### Gerar o APK

```bash
dotnet publish -f net10.0-android \
  -c Release \
  -p:AndroidSdkDirectory="$HOME/Android/Sdk" \
  -p:JavaSdkDirectory="$JAVA_HOME" \
  -p:AndroidPackageFormat=apk
```

O APK assinado para testes pode ser encontrado em:

```text
bin/Release/net10.0-android/publish/
```

O aplicativo foi testado em um **Samsung Galaxy S25 Ultra**, utilizando uma compilação Release.

## Objetivo acadêmico

A atividade propõe complementar um aplicativo de cálculo de combustível, adicionando os campos de marca e modelo do veículo e personalizando a mensagem exibida após o cálculo.

O desenvolvimento permitiu aplicar conhecimentos de:

- Construção de interfaces com XAML.
- Programação orientada a eventos.
- Manipulação de entradas do usuário.
- Estruturas condicionais em C#.
- Compilação e instalação de aplicativos Android.
- Configuração de um ambiente de desenvolvimento .NET MAUI no Linux.
