Atividade 1:
O texto discute a diferença entre programação, ciência da computação e engenharia de software. Enquanto programadores escrevem código e cientistas da computação estudam conceitos teóricos, a engenharia de software envolve aplicar esse conhecimento de forma prática e responsável. Apesar de menos rigorosa que outras engenharias, como a civil ou aeronáutica, a área precisa evoluir, já que o software tem impacto crescente na vida real. 

Atividade 2:
O texto propõe que engenharia de software vai além de programar: inclui processos e ferramentas usados para manter o código valioso ao longo do tempo. A ideia central é que engenharia de software é "programação integrada ao tempo".

Para isso, são destacados três princípios fundamentais:

Tempo e mudança: o código precisa se adaptar ao longo da sua vida útil.

Escala e crescimento: a organização deve evoluir junto com o sistema.

Trocas e custos: decisões precisam equilibrar impactos ao longo do tempo.

Atividade 3:
1. Velocidade de desenvolvimento vs. Qualidade do código
Trade-off: Entregar funcionalidades rapidamente pode significar escrever código menos limpo ou com menos testes.

Exemplo: Em um projeto com prazo apertado, uma equipe pode optar por "gambiarras" para entregar no prazo, sabendo que isso exigirá retrabalho no futuro.

2. Desempenho vs. Legibilidade/Manutenibilidade
Trade-off: Otimizações para deixar o sistema mais rápido podem tornar o código mais difícil de entender e manter.

Exemplo: Substituir código simples por uma solução altamente eficiente, mas complexa, pode prejudicar futuros desenvolvedores que precisem alterá-la.

3. Customização vs. Padronização
Trade-off: Permitir que cada time use suas próprias ferramentas e frameworks pode aumentar a produtividade no curto prazo, mas dificulta a manutenção, integração e troca de membros entre times.

Exemplo: Uma empresa que permite que cada equipe escolha sua própria linguagem pode ter problemas ao integrar sistemas ou migrar desenvolvedores entre projetos.

Atividade 4:
o slide 57 ilustra a importância de entregar valor desde o início no desenvolvimento de produtos. Em vez de construir partes isoladas de um sistema complexo (como peças de um carro que não funcionam sozinhas), a abordagem ideal é entregar versões simples e funcionais (como um skate, depois uma bicicleta) que evoluem gradualmente até o produto final. Assim, o usuário tem uma experiência útil em cada etapa e o projeto se desenvolve de forma iterativa e orientada por feedback.

Atividade 5:
```
public class Hospede {
    private String nome;
    private String documento;

    public Hospede(String nome, String documento) {
        this.nome = nome;
        this.documento = documento;
    }

    public String getNome() {
        return nome;
    }

    public String getDocumento() {
        return documento;
    }

    public String toString() {
        return "Hóspede: " + nome + " | Documento: " + documento;
    }
}

import java.util.ArrayList;

public class Hotel {
    private ArrayList<Hospede> hospedes;

    public Hotel() {
        hospedes = new ArrayList<>();
    }

    public void checkIn(Hospede hospede) {
        hospedes.add(hospede);
        System.out.println("Check-in realizado: " + hospede);
    }

    public void checkOut(String documento) {
        for (Hospede hospede : hospedes) {
            if (hospede.getDocumento().equals(documento)) {
                hospedes.remove(hospede);
                System.out.println("Check-out realizado: " + hospede);
                return;
            }
        }
        System.out.println("Hóspede não encontrado: " + documento);
    }

    public void listarHospedes() {
        System.out.println("Hóspedes atualmente no hotel:");
        for (Hospede hospede : hospedes) {
            System.out.println(hospede);
        }
    }
}

public class TesteHotel {
    public static void main(String[] args) {
        Hotel hotel = new Hotel();

        Hospede h1 = new Hospede("Ana Clara", "RG123456");
        Hospede h2 = new Hospede("Bruno Mendes", "RG789012");
        Hospede h3 = new Hospede("Carla Souza", "RG345678");

        hotel.checkIn(h1);
        hotel.checkIn(h2);
        hotel.checkIn(h3);

        hotel.listarHospedes();

        hotel.checkOut("RG789012");

        hotel.listarHospedes();
    }
}
```
