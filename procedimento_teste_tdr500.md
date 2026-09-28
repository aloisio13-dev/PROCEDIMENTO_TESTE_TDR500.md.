# Procedimento de Teste de Cabo de Sinal com Megger TDR500/3

**Cabo sob teste:** 1P x 1,00 mm²  
**Comprimento estimado:** 1.500 m  
**Equipamento:** Megger TDR500/3 / TDR500/3-CTV  

---

## 1. Preparação e Segurança
* **Desenergização:** Certifique-se de que o cabo sob teste esteja **completamente desenergizado e desconectado** de sensores, transmissores, módulos de E/S ou equipamentos em ambas as extremidades.
* **Inspeção:** Verifique o estado físico das pontas de prova e dos conectores do TDR500/3.

---

## 2. Configuração Inicial no Menu Setup (Ícone da Chave)
Gire a chave seletora do equipamento para o ícone da **chave de boca (Setup)**. Navegue entre as variáveis usando as setas e ajuste os valores movendo o joystick para cima/para baixo:

* **Unidade de Medida (Ícone da Régua):** Selecione **Meters (m)** para obter leituras em metros.
* **Impedância Característica ($Z$):** Ajuste a impedância para **100 $\Omega$**, especificação padrão para cabos de par trançado (*twisted-pair*).
* **Fator de Velocidade ($VF$ / $VoP$):** Ajuste o valor de $VF$ conforme a folha de dados do fabricante do cabo (para cabos de sinal/par trançado, o valor típico é entre 0,66 e 0,70 ou 66%–70%).
* **Contraste e Áudio (Opcionais):** Ajuste o contraste da tela (ícone da lâmpada) e ative o sinal sonoro das teclas (ícone do alto-falante), se necessário.

---

## 3. Conexão do Instrumento
* Conecte as duas pontas de prova do TDR500/3 nos **dois condutores do par (1P)** da extremidade do cabo que será testada.

---

## 4. Seleção do Modo de Operação e Alcance (Range)

### Modo Automático (Recomendado - Fundo Verde - AUTO)
* Gire a chave seletora para o modo **AUTO** (fundo verde).
* No modo **AUTO**, o TDR500/3 otimiza automaticamente a largura de pulso, o ganho e a impedância para a faixa de distância selecionada.
* Ajuste a escala de distância (*Range*) no equipamento para uma faixa superior a **1.500 m** (ex.: 2.000 m ou 3.000 m).
* Ajuste a velocidade de propagação ($VF$) e mova o cursor para medir os eventos no traço.

### Modo Manual (Ajuste Fino - Ícone de Traço Verde)
* Se optar pela **operação manual**, selecione a opção com o ícone de traço no fundo verde.
* Para 1.500 m, selecione manualmente uma largura de pulso mais ampla (como **20 ns**) para garantir maior alcance e ajuste o ganho (níveis 1, 2 ou 3) caso o sinal de retorno apresente atenuação acentuada.

---

## 5. Leitura e Localização de Eventos
1. Mova o **cursor** ao longo do gráfico de forma de onda no display até o ponto de deflexão/evento.
2. **Interpretação da Forma de Onda:**
   * **Reflexão para cima (Positiva):** Indica **circuito aberto** (ex.: extremidade final do cabo ou condutor partido).
   * **Reflexão para baixo (Negativa):** Indica **curto-circuito** (entre os condutores do par) ou falha de isolamento de baixa impedância.
3. Observe o valor numérico exibido no display, que indicará a **distância exata até o evento ou até o fim do cabo** em metros.

---

## 6. Finalização do Teste
* Ao concluir, gire a chave para a posição **OFF**. *(O TDR500/3 desliga-se automaticamente após 5 minutos de inatividade, emitindo um aviso sonoro)*.
