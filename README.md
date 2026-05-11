# Documentação do Projeto: Microinterface de Análise de Crédito

## 1. Introdução à Proposta

Este projeto consiste em uma interface exploratória e interativa desenvolvida para auxiliar analistas de risco na compreensão de como diferentes variáveis macro e microeconômicas impactam a concessão de crédito e o lucro de uma carteira de clientes.

O objetivo central é transformar um dataset estático em um ambiente de simulação dinâmico. A partir dessa interface, o usuário pode:

- Visualizar o lucro obtido em diferentes rodadas de simulação;
- Comparar a influência de parâmetros específicos (como Probabilidade de Inadimplência ou Limite Máximo) entre as simulações;
- Identificar os três principais fatores de influência em cada cenário por meio de pop-ups contextuais;
- Adicionar novos conjuntos de parâmetros para testar hipóteses em tempo real.

---

## 2. Rascunhos Iniciais

A concepção do projeto partiu de um esboço manual focado na organização espacial das informações. O rascunho original (conforme imagem anexa no relatório) estabeleceu os principais elementos da interface.

[imagem do rascunho](image.png)

### Gráficos de barra

As barras foram definidas como representação visual da performance de cada simulação, permitindo observar rapidamente variações de lucro entre experimentos.

### Post-it de influência

Foi concebido como uma solução visual para apresentar detalhes sem sobrecarregar a tela principal. Esse elemento aparece apenas sob demanda, por meio de interação por clique.

### Entrada de dados

Na parte inferior da interface foi previsto um formulário para criação de novos cenários, permitindo a mutabilidade dos parâmetros.

### Linha de comparação

A proposta inicial incluiu uma linha visual conectando as barras, permitindo comparar o comportamento de um parâmetro específico ao longo de todas as simulações.

### Observação de design

Durante a evolução do rascunho para a versão digital, optou-se por uma estética **Dark Mode**, inspirada em interfaces de alta tecnologia. A biblioteca **p5.js** foi adotada para garantir fluidez nas animações e nas interações.

---

## 3. Registro do Resultado Obtido

### Tecnologias utilizadas

- **p5.js** — motor principal para renderização dos gráficos, detecção de interações (hover e clique), animações e manipulação espacial.
- **HTML5 / CSS3** — estrutura da interface, tipografia e organização visual.
- **JavaScript (ES6)** — lógica de processamento de dados, simulação de parâmetros e cálculo heurístico de lucro.

---

## 4. Funcionalidades Implementadas

### Dashboard de simulações

Cada barra representa uma simulação distinta do dataset. O comprimento da barra corresponde ao lucro gerado naquele cenário.

### Overlay de parâmetros

Ao selecionar um parâmetro no menu superior, o sistema desenha uma linha de comparação sobre o conjunto de barras. Essa linha permite observar rapidamente como a variação daquele parâmetro se comporta entre as simulações.

### Sistema de post-it (pop-up)

Ao clicar em uma barra, surge um post-it digital construído com o uso de `push()`, `pop()` e `translate()`. Esse elemento apresenta os três parâmetros de maior influência naquela simulação específica.

### Ranking de influência

A interface pode processar todas as simulações ativas e gerar um ranking global indicando quais parâmetros estão sendo mais determinantes no comportamento do modelo.

### Entrada dinâmica

O sistema permite adicionar novas simulações a partir do preenchimento dos parâmetros do modelo, possibilitando experimentação em tempo real.

### Feedback visual

Pequenas animações e transições foram utilizadas para reforçar a sensação de interatividade e facilitar a leitura das mudanças de estado.

---

## 5. Parâmetros Monitorados

| Parâmetro | Descrição |
|---|---|
| `r_int` | Taxa de interchange |
| `T` | Taxa de utilização média do limite |
| `LGD` | Loss Given Default |
| `Lmax` | Limite máximo |
| `α_k` | Multiplicador máximo de alavancagem |
| `pd_i` | Probabilidade de inadimplência do cliente |
| `Δcp_i` | Capacidade de pagamento líquida do cliente |

---

## 6. Considerações de Implementação

A construção da interface utilizou conceitos fundamentais de computação gráfica presentes no **p5.js**, especialmente:

- **`push()` e `pop()`** para isolamento de estados gráficos;
- **`translate()`** para reposicionamento local de elementos;
- **`rotate()`** para pequenas variações visuais em elementos contextuais;
- **detecção de colisão com mouse** para ativação de pop-ups e interações.

Esses recursos permitiram estruturar a visualização de maneira modular e organizada, facilitando a expansão futura da interface.

---

## 7. Conclusão do Protótipo

O resultado final entrega uma ferramenta que vai além da simples exibição de dados: trata-se de um ambiente de experimentação.

A proposta permite observar o comportamento de múltiplos cenários, comparar parâmetros e explorar hipóteses de forma visual e interativa.

O uso do **p5.js** foi fundamental para construir uma experiência de usuário mais fluida e exploratória, aproximando a interface de um ambiente de análise investigativa, em vez de um dashboard corporativo tradicional.

Como continuidade do projeto, a lógica de influência dos parâmetros poderá ser substituída por um modelo estatístico ou preditivo real, conectando diretamente a interface ao pipeline de análise de crédito.