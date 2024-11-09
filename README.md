# CC2
// Banque2.java
public class Banque2 {

    // Classe Client
    static class Client {
        private String nom;
        private String ville;

        public Client(String nom, String ville) {
            this.nom = nom;
            this.ville = ville;
        }

        public String getNom() {
            return nom;
        }

        public String getVille() {
            return ville;
        }
    }

    // Classe Compte
    static class Compte {
        private double solde;

        public Compte(double solde) {
            this.solde = solde;
        }

        public double getSolde() {
            return solde;
        }

        public void setSolde(double solde) {
            this.solde = solde;
        }

        // Méthode pour ajouter des intérêts
        public double bouclerCompte(double taux) {
            solde += solde * taux;
            return solde;
        }
    }

    public static void main(String[] args) {
        // Données pour les clients et les comptes
        String nom1 = "Geneviève";
        String ville1 = "Genève";
        double solde1 = 300000; // solde initial du premier client

        String nom2 = "Alexandra";
        String ville2 = "Montréal";
        double solde2 = 400000; // solde initial du deuxième client

        // Taux d'intérêt pour chaque client
        double taux1 = 0.015; // taux pour le premier client (1.5%)
        double taux2 = 0.027; // taux pour le deuxième client (2.7%)

        // Création des clients
        Client client1 = new Client(nom1, ville1);
        Client client2 = new Client(nom2, ville2);

        // Création des comptes pour chaque client
        Compte compte1 = new Compte(solde1);
        Compte compte2 = new Compte(solde2);

        // Affichage des données initiales
        System.out.println("Client: " + client1.getNom() + ", Ville: " + client1.getVille() + ", Solde initial: " + compte1.getSolde() + " francs.");
        System.out.println("Client: " + client2.getNom() + ", Ville: " + client2.getVille() + ", Solde initial: " + compte2.getSolde() + " francs.");

        // Application des intérêts et affichage des nouveaux soldes
        double nouveauSolde1 = compte1.bouclerCompte(taux1);
        double nouveauSolde2 = compte2.bouclerCompte(taux2);

        System.out.println("Nouveau solde de " + client1.getNom() + " après application des intérêts: " + nouveauSolde1 + " francs.");
        System.out.println("Nouveau solde de " + client2.getNom() + " après application des intérêts: " + nouveauSolde2 + " francs.");
    }
}


