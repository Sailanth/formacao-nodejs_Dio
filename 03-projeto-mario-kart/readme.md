<h1>Desafio de projeto do Felipão: Mario Kart.JS</h1>

  <table>
        <tr>
            <td>
                <img src="./docs/header.gif" alt="Mario Kart" width="200">
            </td>
            <td>
                <b>Objetivo:</b>
                <p>Mario Kart é uma série de jogos de corrida desenvolvida e publicada pela Nintendo. Nosso desafio será criar uma lógica de um jogo de vídeo game para simular corridas de Mario Kart, levando em consideração as regras e mecânicas abaixo.</p>
            </td>
        </tr>
    </table>

<h2>Players</h2>
      <table style="border-collapse: collapse; width: 800px; margin: 0 auto;">
        <tr>
            <td style="border: 1px solid black; text-align: center;">
                <p>Mario</p>
                <img src="./docs/mario.gif" alt="Mario Kart" width="60" height="60">
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Velocidade: 4</p>
                <p>Manobrabilidade: 3</p>
                <p>Poder: 3</p>
            </td>
             <td style="border: 1px solid black; text-align: center;">
                <p>Peach</p>
                <img src="./docs/peach.gif" alt="Mario Kart" width="60" height="60">
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Velocidade: 3</p>
                <p>Manobrabilidade: 4</p>
                <p>Poder: 2</p>
            </td>
              <td style="border: 1px solid black; text-align: center;">
                <p>Yoshi</p>
                <img src="./docs/yoshi.gif" alt="Mario Kart" width="60" height="60">
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Velocidade: 2</p>
                <p>Manobrabilidade: 4</p>
                <p>Poder: 3</p>
            </td>
            <td style="border: 1px solid black; text-align: center;">
              <p>Toad</p>
              <img src="./docs/toad.gif" alt="Mario Kart" width="60" height="60">
            </td>
            <td style="border: 1px solid black; text-align: center;">
              <p>Velocidade: 3</p>
              <p>Manobrabilidade: 5</p>
              <p>Poder: 2</p>
            </td>
        </tr>
        <tr>
            <td style="border: 1px solid black; text-align: center;">
                <p>Bowser</p>
                <img src="./docs/bowser.gif" alt="Mario Kart" width="60" height="60">
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Velocidade: 5</p>
                <p>Manobrabilidade: 2</p>
                <p>Poder: 5</p>
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Luigi</p>
                <img src="./docs/luigi.gif" alt="Mario Kart" width="60" height="60">
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Velocidade: 3</p>
                <p>Manobrabilidade: 4</p>
                <p>Poder: 4</p>
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Donkey Kong</p>
                <img src="./docs/dk.gif" alt="Mario Kart" width="60" height="60">
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Velocidade: 2</p>
                <p>Manobrabilidade: 2</p>
                <p>Poder: 5</p>
            </td>
        </tr>
    </table>

<p></p>

<h3>🕹️ Regras & mecânicas:</h3>

<b>Jogadores:</b>

<input type="checkbox" id="jogadores-item" />
<label for="jogadores-item">O Computador deve receber dois personagens para disputar a corrida em um objeto cada</label>

<b>Pistas:</b>

<ul>
  <li><input type="checkbox" id="pistas-1-item" /> <label for="pistas-1-item">Os personagens irão correr em uma pista aleatória de 5 rodadas</label></li>
  <li><input type="checkbox" id="pistas-2-item" /> <label for="pistas-2-item">A cada rodada, será sorteado um bloco da pista que pode ser uma reta, curva ou confronto</label>
    <ul>
      <li><input type="checkbox" id="pistas-2-1-item" /> <label for="pistas-2-1-item">Caso o bloco da pista seja uma RETA, o jogador deve jogar um dado de 6 lados e somar o atributo VELOCIDADE, quem vencer ganha um ponto</label></li>
      <li><input type="checkbox" id="pistas-2-2-item" /> <label for="pistas-2-2-item">Caso o bloco da pista seja uma CURVA, o jogador deve jogar um dado de 6 lados e somar o atributo MANOBRABILIDADE, quem vencer ganha um ponto</label></li>
      <li><input type="checkbox" id="pistas-2-3-item" /> <label for="pistas-2-3-item">Caso o bloco da pista seja um CONFRONTO, o jogador deve jogar um dado de 6 lados e somar o atributo PODER, quem perder, perde um ponto</label></li>
      <li><input type="checkbox" id="pistas-2-3-item" /> <label for="pistas-2-3-item">Nenhum jogador pode ter pontuação negativa (valores abaixo de 0)</label></li>
    </ul>
  </li>
</ul>

<b>Condição de vitória:</b>

<input type="checkbox" id="vitoria-item" />
<label for="vitoria-item">Ao final, vence quem acumulou mais pontos</label>

## Novas Implementações no Código

### 1. Seleção de Personagens Dinâmica

Agora, em vez de `player1` e `player2` serem fixos, os jogadores podem escolher seus personagens de uma lista predefinida (`characters`).

*   **Array `characters`:** Uma lista de objetos JavaScript, onde cada objeto representa um personagem com suas `NOME`, `VELOCIDADE`, `MANOBRABILIDADE`, `PODER` e `PONTOS` iniciais.
*   **Função `main()`:**
    *   Exibe todos os personagens disponíveis com seus respectivos números.
    *   Pede ao **Jogador 1** para escolher um personagem pelo número.
    *   Pede ao **Jogador 2** para escolher um personagem diferente do **Jogador 1**.
    *   Cria cópias dos personagens escolhidos para `player1` e `player2`, garantindo que cada um comece com 0 pontos para a corrida atual (`{ ...characters[index], PONTOS: 0 }`).

### 2. Novas Regras de Confronto

A lógica do bloco `CONFRONTO` foi aprimorada para incluir bônus e penalidades:

*   **Vencedor do Confronto:**
    *   Recebe um **turbo (+1 ponto)** na sua pontuação.
    *   Exemplo de log: "`Mario` venceu o confronto e ganhou um turbo (+1 ponto)!"
*   **Perdedor do Confronto:**
    *   Sofre uma penalidade aleatória: um **casco (-1 ponto)** ou uma **bomba (-2 pontos)**.
    *   **Nova Função `getRandomPenalty()`:** Sorteia entre "casco" (valor 1) ou "bomba" (valor 2) com 50% de chance para cada um.
    *   A pontuação do perdedor é subtraída pelo valor da penalidade, mas **nunca pode ser menor que zero** (garantido por `Math.max(0, character.PONTOS - penalty.value)`).
    *   Exemplo de log: "`Luigi` perdeu 1 ponto(s) devido a um(a) casco!"
*   **Confronto Empatado:** Se os `powerResult` forem iguais, nenhum ponto é ganho ou perdido.

### 3. Ajuste na Pontuação Normal (Fora do Confronto)

*   A lógica de pontuação padrão (ganhar 1 ponto para o `totalTestSkill` maior) agora só é aplicada se o bloco **não for** um `CONFRONTO`. Isso evita que os pontos do confronto sejam somados aos pontos normais na mesma rodada.

### 4. Tratamento de Input para Node.js

*   **`readline-sync`:** Para permitir a entrada de dados do usuário em um ambiente Node.js (como o VS Code), o pacote `readline-sync` foi importado e usado na função `simulateInput` para substituir a função `prompt()` que é exclusiva de navegadores.
