atividade 5:

```public class Hospede {
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
}```

```import java.util.ArrayList;

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
```
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
