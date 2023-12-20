// Variáveis do jogo
let pontuacaoHeroi = 0;
let pontuacaoOponente = 0;
let numeroDeRodadas = 10;

// Função para simular uma rodada do jogo
function jogarRodada() {
    // Gera uma pontuação aleatória para o jogador e o oponente
    const pontuacaoHeroiRodada = Math.floor(Math.random() * 12) + 1;
    const pontuacaoOponenteRodada = Math.floor(Math.random() * 12) + 1;

    // Atualiza a pontuação total
    pontuacaoHeroi += pontuacaoHeroiRodada;
    pontuacaoOponente += pontuacaoOponenteRodada;

    // Exibe os resultados da rodada
    console.log(`Rodada: Heroi ${pontuacaoHeroiRodada} - ${pontuacaoOponenteRodada} Oponente`);

    // Verifica o vencedor da rodada
    if (pontuacaoHeroiRodada > pontuacaoOponenteRodada) {
        console.log("Você venceu esta rodada!");
    } else if (pontuacaoOponenteRodada > pontuacaoHeroiRodada) {
        console.log("O oponente venceu esta rodada!");
    } else {
        console.log("Esta rodada terminou em empate!");
    }
}

// Laço de repetição para simular várias rodadas
for (let i = 1; i <= numeroDeRodadas; i++) {
    console.log(`\n=== Rodada ${i} ===`);
    jogarRodada();
}

// Exibe o resultado final do jogo
console.log("\n=== Resultado Final ===");
console.log(`Sua pontuação: ${pontuacaoHeroi}`);
console.log(`Pontuação do oponente: ${pontuacaoOponente}`);

// Determina o vencedor do jogo
if (pontuacaoHeroi > pontuacaoOponente) {
    console.log("Parabéns! Você venceu o jogo!");
} else if (pontuacaoOponente > pontuacaoHeroi) {
    console.log("O oponente venceu o jogo. Tente novamente!");
} else {
    console.log("O jogo terminou em empate!");
}

classificadorDeVitorias(pontuacaoHeroi);

// Função para classificar o jogador com base no total de vitórias
function classificadorDeVitorias(totalVitorias) {
    console.log("\n=== Classificação ===");
	const mensagemFinal = ("O Heroi está no Rank: ")

    if (totalVitorias < 10) {
        console.log(mensagemFinal + "Ferro");
    } else if (totalVitorias >= 10 && totalVitorias <= 20) {
        console.log(mensagemFinal + "Bronze");
    } else if (totalVitorias >= 21 && totalVitorias <= 50) {
        console.log(mensagemFinal + "Prata");
    } else if (totalVitorias >= 51 && totalVitorias <= 80) {
        console.log(mensagemFinal + "Ouro");
    } else if (totalVitorias >= 81 && totalVitorias <= 90) {
        console.log(mensagemFinal + "Diamante");
    } else if (totalVitorias >= 91 && totalVitorias <= 100) {
        console.log(mensagemFinal + "Lendário");
    } else {
        console.log(mensagemFinal + "Imortal");
    }
}
