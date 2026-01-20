# 🚂 Monitoramento Histórico - Estrada de Ferro Santa Catharina (1936)

Este projeto é um simulador em tempo real que recria o tráfego ferroviário da **Estrada de Ferro Santa Catharina (EFSC)** com base nos horários oficiais de **outubro de 1936**. A aplicação utiliza o horário atual do sistema para calcular a posição aproximada das composições, oferecendo uma janela interativa para o passado ferroviário catarinense.

---

## 📋 Sobre o Projeto

O simulador é fundamentado nos dados históricos publicados pelo jornal *A Cidade* em 26 de setembro de 1936. Ele cobre a **Linha Principal** (Blumenau a Barra do Trombudo) e o **Ramal de Hammonia** (Subida a Ibirama).

### Principais Características
* **Relógio Analógico Retrô:** Um relógio estilizado que segue o horário local para sincronizar a simulação.
* **Dinâmica de Movimento:** Os trens movem-se proporcionalmente entre as estações com base no horário real de partida e chegada.
* **Diferenciação de Composições:** Visualização distinta para trens Ascendentes (sentido interior - Vermelho) e Descendentes (sentido Blumenau - Azul).
* **Fidelidade Histórica:** Inclui trens de passageiros (P), mistos (M) e composições dominicais.

---

## 🛠️ Tecnologias Utilizadas

O projeto foi desenvolvido de forma "Vanilla" (pura), sem dependências externas, garantindo leveza e compatibilidade:

* **HTML5:** Estrutura semântica dos painéis e trilhos.
* **CSS3:** Estilização com variáveis (`:root`), Flexbox e transformações para o visual "vintage" e o funcionamento do relógio analógico.
* **JavaScript (ES6):** Lógica de conversão de tempo, cálculo de posicionamento em tempo real e manipulação dinâmica do DOM.

---

## 🛤️ Malha Ferroviária Coberta

### Estações da Linha Principal (104.3 km)
| Estação | Quilometragem (Km) |
| :--- | :--- |
| Blumenau | 0.0 |
| Indayal | 22.0 |
| Subida | 63.1 |
| Rio do Sul | 97.8 |
| Barra do Trombudo | 104.3 |

### Ramal de Hammonia (12.0 km)
* **Conexão:** Subida (Km 0) ↔ Hammonia/Ibirama (Km 12.0)

---

## 📖 Lógica de Funcionamento

O sistema opera através de um loop de atualização que executa a cada segundo:

1.  **Captura do Tempo:** Obtém o horário atual e o dia da semana do sistema do usuário.
2.  **Filtragem:** Verifica quais trens estão ativos de acordo com o dia (ex: Trens `M` não circulam aos domingos).
3.  **Cálculo de Progresso:** A posição do trem é definida pela fórmula de interpolação linear:
    
    $$P = \frac{T_{atual} - T_{inicio}}{T_{fim} - T_{inicio}}$$
    
    Onde $P$ representa o progresso (de 0 a 1) entre o ponto de partida e o destino.
4.  **Renderização:** O elemento visual é posicionado dinamicamente no mapa conforme a porcentagem calculada sobre a extensão da linha.

---

## 🚀 Como Executar

1.  Faça o download do arquivo `index.html`.
2.  Abra o arquivo em qualquer navegador moderno (Chrome, Firefox, Edge, Safari).
3.  **Nota:** Como o simulador usa o tempo real, se você abrir em um horário sem trens previstos (ex: madrugada), o mapa estará vazio. 
    * *Dica: Para testar o movimento, você pode alterar temporariamente o horário do seu computador para as 09:30 de um dia útil.*

---

## ✒️ Créditos e Fontes

* **Desenvolvimento:** Daniel Baumann.
* **Dados Históricos:** [Hemeroteca Digital Brasileira](http://memoria.bn.gov.br/DocReader/882860/2706) - Jornal "A Cidade" (1936).
* **Objetivo:** Preservação da memória ferroviária e resgate técnico da EFSC.

---

> **Aviso Técnico:** Este projeto é uma ferramenta de resgate histórico e educacional. O movimento dos trens é uma representação linear simplificada para fins de visualização web e não considera paradas técnicas intermediárias de carga.