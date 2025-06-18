# super-trunfo
#include <stdio.h>
#include <string.h>

// Estrutura de uma carta do jogo
struct Pais {
    char nome[30];
    float pib;             // Produto Interno Bruto (em bilhões)
    float area;            // Área em km²
    int populacao;         // População
    int pontosTuristicos;  // Pontos turísticos (valor simbólico)
};

// Função que compara os atributos
void comparar(struct Pais jogador, struct Pais computador, char atributo[]) {
    printf("\n--- Carta do Computador ---\n");
    printf("País: %s\n", computador.nome);
    printf("PIB: %.2f bilhões\n", computador.pib);
    printf("Área: %.2f km²\n", computador.area);
    printf("População: %d\n", computador.populacao);
    printf("Pontos Turísticos: %d\n", computador.pontosTuristicos);

    if (strcmp(atributo, "pib") == 0) {
        if (jogador.pib > computador.pib)
            printf("\nVocê venceu! Seu PIB é maior.\n");
        else if (jogador.pib < computador.pib)
            printf("\nVocê perdeu! O PIB do computador é maior.\n");
        else
            printf("\nEmpate! Os PIBs são iguais.\n");
    }
    else if (strcmp(atributo, "area") == 0) {
        if (jogador.area > computador.area)
            printf("\nVocê venceu! Sua área é maior.\n");
        else if (jogador.area < computador.area)
            printf("\nVocê perdeu! A área do computador é maior.\n");
        else
            printf("\nEmpate! As áreas são iguais.\n");
    }
    else if (strcmp(atributo, "populacao") == 0) {
        if (jogador.populacao > computador.populacao)
            printf("\nVocê venceu! Sua população é maior.\n");
        else if (jogador.populacao < computador.populacao)
            printf("\nVocê perdeu! A população do computador é maior.\n");
        else
            printf("\nEmpate! As populações são iguais.\n");
    }
    else if (strcmp(atributo, "pontos") == 0) {
        if (jogador.pontosTuristicos > computador.pontosTuristicos)
            printf("\nVocê venceu! Tem mais pontos turísticos.\n");
        else if (jogador.pontosTuristicos < computador.pontosTuristicos)
            printf("\nVocê perdeu! O computador tem mais pontos turísticos.\n");
        else
            printf("\nEmpate! Mesmo número de pontos turísticos.\n");
    }
    else {
        printf("\nAtributo inválido! Use: pib, area, populacao ou pontos\n");
    }
}

int main() {
    // Carta do jogador: Brasil
    struct Pais brasil = {"Brasil", 2200.5, 8515767.0, 215000000, 12};

    // Carta do computador: EUA
    struct Pais eua = {"Estados Unidos", 21400.0, 9833517.0, 331000000, 25};

    struct Pais cartaJogador = brasil;
    struct Pais cartaComputador = eua;

    char atributo[20];

    // Exibir carta do jogador
    printf("===== SUA CARTA =====\n");
    printf("País: %s\n", cartaJogador.nome);
    printf("PIB: %.2f bilhões\n", cartaJogador.pib);
    printf("Área: %.2f km²\n", cartaJogador.area);
    printf("População: %d\n", cartaJogador.populacao);
    printf("Pontos Turísticos: %d\n", cartaJogador.pontosTuristicos);

    // Jogador escolhe atributo
    printf("\nEscolha um atributo para comparar (pib, area, populacao, pontos): ");
    scanf("%s", atributo);

    // Chamada da função de comparação
    comparar(cartaJogador, cartaComputador, atributo);

    return 0;
}

 
