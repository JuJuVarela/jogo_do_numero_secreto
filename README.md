# 🎮 Jogo do Número Secreto

Um projeto simples de adivinhação desenvolvido em **JavaScript**, que desafia o usuário a encontrar o número secreto escolhido aleatoriamente dentro de um limite pré-definido.

## ✨ Recursos Principais

* **Adivinhação Interativa:** O jogador tenta adivinhar um número secreto entre 1 e 10.
* **Dicas de Comparação:** O jogo indica se o palpite do usuário é **maior** ou **menor** que o número secreto.
* **Contagem de Tentativas:** Acompanhamento do número de tentativas necessárias para o acerto.
* **Experiência de Voz:** Utiliza a função `responsiveVoice.speak` para **falar** as mensagens do jogo em Português Brasileiro (necessita da integração da biblioteca `responsiveVoice`).
* **Controle de Sorteio:** Garante que os números já sorteados não se repitam até que todo o limite (`numeroLimite`) seja atingido, reiniciando o ciclo de números em seguida.

## 🚀 Como Jogar

1.  **Interface:** A interface do jogo deve conter um campo de entrada (`<input>`), um botão para enviar o chute (que chama a função `verificarChute()`) e um botão de reiniciar com o `id="reiniciar"`.
2.  **Início:** Ao carregar, o jogo define um `numeroSecreto` e exibe a mensagem inicial (falada e escrita).
3.  **Adivinhe:** Insira um número no campo e chute.
4.  **Feedback:** O jogo dirá se você está **perto** ou se **acertou**.
5.  **Reinicie:** Após acertar, o botão **Reiniciar Jogo** é ativado para começar uma nova rodada.
6.  ```html
    jogodonumerosecreto-nu-silk.vercel.app 

## ⚙️ Funções Chave do Código

O código está estruturado em torno de funções para gerenciar a interface, a lógica do jogo e o sorteio de números.

| Função | Descrição |
| :--- | :--- |
| `exibirTextoNaTela(tag, texto)` | **Manipulação do DOM** e **Voz**. Altera o texto de um elemento HTML (`tag`) e o pronuncia usando o `responsiveVoice.speak`. |
| `exibirMensagemInicial()` | Exibe o título principal e a instrução de adivinhação. |
| `verificarChute()` | Captura o `input`, compara-o com `numeroSecreto`, fornece feedback, atualiza as `tentativas` e habilita o botão de reiniciar se for o chute correto. |
| `gerarNumeroAleatorio()` | Implementa a **lógica de sorteio**. Gera um número, verifica se ele já está na `listaDeNumerosSorteados`. Se sim, chama a si mesma recursivamente. Se não, adiciona-o à lista. |
| `limparCampo()` | Limpa o conteúdo do campo de entrada (`<input>`). |
| `reiniciarJogo()` | Prepara o jogo para uma nova rodada: gera novo número secreto, limpa o campo, reseta as tentativas e desabilita o botão de reiniciar. |

## 🧩 Variáveis Globais

| Variável | Uso |
| :--- | :--- |
| `listaDeNumerosSorteados` | Array (lista) que armazena os números já escolhidos na rodada atual para evitar repetição. |
| `numeroLimite` | Define o valor máximo para a adivinhação (padrão: `10`). |
| `numeroSecreto` | Armazena o número que o jogador precisa adivinhar. |
| `tentativas` | Contador que registra o número de palpites. |

---

## ⚠️ Requisitos

Para que a funcionalidade de **voz** (`responsiveVoice.speak`) funcione corretamente, você deve incluir o script da biblioteca **Responsive Voice Text-To-Speech** no seu arquivo HTML.

```html
<script src="[https://code.responsivevoice.org/responsivevoice.js?key=YOUR_API_KEY](https://code.responsivevoice.org/responsivevoice.js?key=YOUR_API_KEY)"></script>
