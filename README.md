# Guia de Teste e Diagnóstico de Cabos de Sinal com Megger TDR500/3

> **Procedimento Operacional Padrão (POP)** para testes de refletometria no domínio do tempo (TDR) em cabos de sinalização e instrumentação utilizando o refletômetro **Megger TDR500/3**.

---

## 📌 Visão Geral do Projeto

Este repositório contém o procedimento detalhado para execução de testes de continuidade, localização de falhas e verificação do comprimento em cabos de sinal elétrico de **1 par (1P x 1,00 mm²)** com comprimento nominal de **1.500 metros**.

O **Megger TDR500/3** envia um pulso elétrico pelo cabo e analisa o sinal refletido para identificar descontinuidades de impedância, permitindo localizar com precisão cortes, curtos-circuitos ou variações de características do cabo.

---

## 📋 Especificações do Teste

| Parâmetro | Valor / Configuração Recomendada |
| :--- | :--- |
| **Equipamento** | Megger TDR500/3 ou TDR500/3-CTV |
| **Cabo sob Teste** | 1P x 1,00 mm² (Par Trançado de Sinal) |
| **Comprimento Nominal** | 1.500 metros |
| **Unidade de Medida** | Metros ($m$) |
| **Impedância Característica ($Z$)** | $100\,\Omega$ |
| **Fator de Velocidade ($VF$ / $VoP$)** | $0,66$ a $0,70$ ($66\%$ a $70\%$) |
| **Modo de Operação** | AUTO (Fundo Verde) ou Manual |

---

## ⚙️ Procedimento Passo a Passo

### 1. Preparação e Segurança
- [x] **Desenergização:** Garanta que o cabo esteja **completamente desenergizado e desconectado** em ambas as extremidades (sensores, transmissores, módulos de E/S ou CLP).
- [x] **Inspeção Física:** Verifique a integridade dos conectores BNC, garras jacaré e pontas de prova.

### 2. Configuração Inicial no Menu Setup (Ícone da Chave)
Gire a chave seletora para a opção de **Setup (Chave de boca)** e ajuste as variáveis usando as setas e o joystick:
1. **Unidade (Ícone da Régua):** Defina para **Meters (m)**.
2. **Impedância ($Z$):** Ajuste em **$100\,\Omega$** (padrão para par trançado de sinal).
3. **Fator de Velocidade ($VF$):** Insira o valor conforme o *datasheet* do fabricante (ex.: $0,67$).
4. **Contraste / Áudio:** Ajuste se necessário para melhor visualização em campo.

### 3. Conexão no Cabo
- Conecte as duas garras de prova nos **dois condutores do par (1P)** na extremidade de teste.

### 4. Seleção da Escala e Modo de Medição
* **Modo Automático (Recomendado - AUTO):**
  * Gire o seletor para **AUTO** (fundo verde). O equipamento otimiza automaticamente a largura de pulso (2 ns, 6 ns ou 20 ns), o ganho e a impedância.
  * Ajuste a escala de distância (*Range*) para um valor superior ao comprimento esperado (ex.: **2.000 m** ou **3.000 m**).
* **Modo Manual:**
  * Para distâncias longas ($1.500\,\text{m}$), utilize largura de pulso mais ampla (**20 ns**) e eleve o ganho para compensar a atenuação do sinal.
  * Para distâncias curtas ou inspeção inicial ($< 25\,\text{m}$), selecione escalas menores para ativar pulsos estreitos (**2 ns**).

### 5. Leitura e Análise da Forma de Onda
1. Desloque o **cursor** até o ponto de deflexão da curva exibida na tela.
2. Identifique o tipo de evento através do sentido da reflexão:

| Tipo de Deflexão | Significado Elétrico | Causas Prováveis |
| :---: | :--- | :--- |
| ⬆️ **Para Cima (Positiva)** | Alta Impedância / Circuito Aberto | Condutor partido, cabo cortado, conector solto ou fim do cabo. |
| ⬇️ **Para Baixo (Negativa)** | Baixa Impedância / Curto-Circuito | Condutores em curto, esmagamento severo ou infiltração de água. |

---

## 🛠️ Diagnóstico Avançado & Solução de Problemas

### Estudo de Caso: Falha Próxima ao Instrumento (*Dead Zone*)

> **Sintoma:** Ao testar o cabo na escala de **2.000 m**, nenhuma deflexão é observada. Ao reduzir a escala para **25 m**, surge uma deflexão nítida a **1,5 m**.

* **Causa Raiz:** Nas escalas longas ($2.000\,\text{m}$), o TDR injeta um pulso elétrico largo ($20\,\text{ns}$) que mascara reflexões nos primeiros metros do cabo (zona morta / *dead zone*). Ao mudar para a escala de $25\,\text{m}$, o equipamento seleciona um pulso ultracurto ($2\,\text{ns}$), revelando a falha próxima.
* **Diagnóstico:** A deflexão a $1,5\,\text{m}$ indica que o sinal elétrico é totalmente refletido antes de percorrer o restante do cabo.
* **Ação Corretiva:** 
  1. Cortar e remover o trecho danificado nos primeiros $2\,\text{m}$ do cabo.
  2. Refazer a decapagem e conexão das pontas de prova.
  3. Repetir o teste na escala de $25\,\text{m}$ para confirmar que a falha desapareceu.
  4. Mudar para a escala de $2.000\,\text{m}$ para realizar a leitura completa dos $1.498\,\text{m}$ restantes.

---

## 📁 Estrutura de Arquivos do Repositório

```text
.
├── README.md                          # Este arquivo de documentação
└── docs/
    └── procedimento_teste_tdr500.md   # Procedimento resumido para impressão
```

---

## 📄 Licença

Este documento é fornecido como Guia de Operação de Campo para técnicos e engenheiros de instrumentação e manutenção. Sinta-se à vontade para adaptar este repositório às especificações do seu projeto.
