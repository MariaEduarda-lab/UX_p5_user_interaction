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

A concepção do projeto partiu de um esboço manual focado na organização espacial das informações. O rascunho original estabeleceu os principais elementos da interface.

### Gráficos de barra

As barras foram definidas como representação visual da performance de cada simulação, permitindo observar rapidamente variações de lucro entre experimentos.

### Post-it de influência

Foi concebido como uma solução visual para apresentar detalhes sem sobrecarregar a tela principal. Esse elemento aparece apenas sob demanda, por meio de interação por clique.

### Entrada de dados

Na parte inferior da interface foi previsto um formulário para criação de novos cenários, permitindo a mutabilidade dos parâmetros.

### Linha de comparação

A proposta inicial incluiu uma linha visual conectando as barras, permitindo comparar o comportamento de um parâmetro específico ao longo de todas as simulações.

[imagem do rascunho](image.png)

---

## 3. Tecnologias Utilizadas

- **p5.js** — motor principal para renderização dos gráficos, detecção de interações (hover e clique), animações e manipulação espacial.
- **HTML5 / CSS3** — estrutura da interface, tipografia e organização visual.
- **JavaScript (ES6)** — lógica de processamento de dados, simulação de parâmetros e cálculo heurístico de lucro.

---

## 4. Funcionalidades Implementadas

### Dashboard de simulações

Cada barra representa uma simulação distinta; o comprimento corresponde ao lucro gerado.

### Overlay de parâmetros

Linha de comparação dinâmica que atravessa o gráfico para correlacionar variáveis selecionadas.

### Sistema de post-it (pop-up)

Detalha os três parâmetros de maior influência em cada barra através de transformações espaciais isoladas.

### Ranking de influência

Processamento global que identifica quais parâmetros são estatisticamente mais determinantes no modelo atual.

### Entrada dinâmica

Permite a inserção de novos dados e o teste de hipóteses sem necessidade de recarregar a aplicação.

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

## 6. O Valor Estratégico da Visualização

A importância desta interface reside na capacidade de humanizar dados complexos. Para um analista de crédito, números isolados em uma planilha podem mascarar tendências.

Esta visualização gera valor através de:

### Aceleração do insight

Ao utilizar o **overlay de parâmetros**, o analista não precisa comparar tabelas manualmente. A correlação visual entre o aumento do limite (`Lmax`) e a queda no lucro torna-se imediatamente evidente por meio da inclinação da linha de tendência.

### Análise de sensibilidade intuitiva

Ao alterar valores e criar novos cenários, o usuário realiza o chamado **what-if analysis** (análise de cenários).

O valor surge ao permitir que o analista descubra o ponto de ruptura da carteira — por exemplo, até que ponto a inadimplência pode crescer antes que o lucro seja anulado — em um ambiente seguro e visual.

### Identificação de causas raiz

O sistema de **post-its de influência** reduz a sobrecarga cognitiva.

Em vez de analisar simultaneamente sete variáveis, o analista concentra sua atenção nas três que exercem maior impacto em cada cenário, permitindo decisões mais rápidas e assertivas.

---

## 7. Conclusão

O resultado final entrega uma ferramenta que vai além da exibição de dados: trata-se de um ambiente de experimentação.

Ao permitir que o analista interaja, altere e crie dados, a interface deixa de ser um relatório estático e passa a funcionar como uma extensão do raciocínio lógico do profissional.

O uso do **p5.js** transformou o processo de análise de risco em uma experiência investigativa fluida, reduzindo a barreira entre a complexidade matemática do modelo e a tomada de decisão estratégica.