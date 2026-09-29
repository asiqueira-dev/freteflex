# 🚚 FreteFlex

## Sistema de Cálculo de Frete

**FreteFlex** é um sistema de cálculo de frete desenvolvido com **Java e
Spring Boot**, que permite calcular o custo de envio de pacotes
utilizando diferentes estratégias de cálculo.

O sistema oferece duas principais opções de frete:

-   **Standard (Normal)**
-   **Express (Expresso)**

Cada opção utiliza uma fórmula diferente para calcular o custo com base
no **peso do pacote** e na **distância de envio**.

------------------------------------------------------------------------

## 📋 Regras de Negócio

### 📦 Frete Standard (Normal)

O Frete Standard oferece um custo mais acessível, sendo adequado para
entregas que não possuem urgência.

**Fórmula de cálculo:**

``` text
custo = peso * 1.0 + distância * 0.5
```

### ⚡ Frete Express (Expresso)

O Frete Express possui um custo maior, sendo destinado a entregas mais
rápidas e prioritárias.

**Fórmula de cálculo:**

``` text
custo = peso * 1.5 + distância * 0.75
```

------------------------------------------------------------------------

## 📥 Parâmetros de Entrada

Para realizar o cálculo do frete, são utilizados os seguintes
parâmetros:

  Parâmetro    Descrição                                        Exemplo
  ------------ ------------------------------------------------ -----------
  `weight`     Peso do pacote em quilogramas (kg)               `10`
  `distance`   Distância total da entrega em quilômetros (km)   `100`
  `type`       Tipo de frete (`standard` ou `express`)          `express`

------------------------------------------------------------------------

## ⚙️ Processo de Cálculo de Frete

1.  O usuário informa o **peso do pacote**.
2.  Informa a **distância da entrega**.
3.  Escolhe o tipo de frete: `standard` ou `express`.
4.  O sistema seleciona a implementação apropriada do
    `ShippingCalculator`.
5.  O custo é calculado utilizando a fórmula correspondente ao tipo de
    frete selecionado.
6.  O valor calculado é retornado pela API.

------------------------------------------------------------------------

## 🌐 Endpoint REST

### Calcular Frete

``` http
GET /shipping/calculate
```

### Parâmetros de consulta

-   `weight`: Peso do pacote.
-   `distance`: Distância de envio.
-   `type`: Tipo de frete (`standard` ou `express`).

### Exemplo de requisição

``` http
GET /shipping/calculate?weight=10&distance=100&type=express
```

### Retorno

O sistema retorna o custo calculado através do campo:

``` text
shippingCost
```

------------------------------------------------------------------------

## 🧮 Exemplo de Uso

Um usuário deseja enviar um pacote com as seguintes características:

-   **Peso:** 10 kg
-   **Distância:** 100 km
-   **Tipo de frete:** `express`

### Frete Standard

``` text
custo = 10 * 1.0 + 100 * 0.5
custo = 10 + 50
custo = 60
```

**Valor do Frete Standard: 60**

### Frete Express

``` text
custo = 10 * 1.5 + 100 * 0.75
custo = 15 + 75
custo = 90
```

**Valor do Frete Express: 90**

------------------------------------------------------------------------

## 🛠️ Tecnologias Utilizadas

-   Java
-   Spring Boot
-   Maven
-   API REST
-   Programação Orientada a Objetos
-   Strategy Pattern

------------------------------------------------------------------------

## 🎓 Formação

Projeto realizado durante o curso de **Formação Spring Boot** da **Build
& Run**.

🌐 **Site:** https://buildrun.com.br/

------------------------------------------------------------------------

## 👨‍💻 Autor

Desenvolvido por **Anderson Lopes de Siqueira**.

🌐 **Site pessoal:** https://andersonsiqueira.com
