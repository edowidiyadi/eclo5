package veckouppgift1;
class Person {

    private String en; //Efternamn
    private String fn; //Förnamn
    private String pnr;//Personnummer

    public Person(String en, String fn, String pnr) {
        this.en = en;
        this.fn = fn;
        this.pnr = pnr;
    }

    public String toString() {
        return "Namn: " + fn + " " + en + "\nPersonnummer: " + pnr;
    }
}

class Arbetare extends Person {

    private String antnr; //anställningsnummer
    private String antd;  //anställningsdatum
    private String antn;  //namn på anställningen
    private String uppd;  //arbetsuppgifter

    public Arbetare(String en, String fn, String pnr, String antnr, String antd, String antn, String uppd) {
        super(en, fn, pnr); //en, fn, pnr
        this.antnr = antnr;
        this.antd = antd;
        this.antn = antn;
        this.uppd = uppd;
    }

    public String toString() {
        return super.toString()+ "\nAnställningsnummer: " + antnr + "\nAnställningsdatum: " + antd
                + "\nID Namn: " + antn + "\nArbetsuppgifter: " + uppd;
    }

    public int lon(int lön) {
        return 0;
    }
}

class Larare extends Arbetare {

    public Larare(String en, String fn, String pnr, String antnr, String antd, String antn, String uppd) {
        super(en, fn, pnr, antnr, antd, antn, uppd);
    }

    public String toString() {
        return super.toString();
    }

    public int lon(int lön) {
        return 10000+lön;
    }
}

class Chef extends Arbetare {

    public Chef(String en, String fn, String pnr, String antnr, String antd, String antn, String uppd) {
        super(en, fn, pnr, antnr, antd, antn, uppd);
    }

    public String toString() {
        return super.toString();
    }

    public int lon(int lön) {
        return 20000+lön;
    }
}

class AdmArbetare extends Arbetare {

    public AdmArbetare(String en, String fn, String pnr, String antnr, String antd, String antn, String uppd) {
        super(en, fn, pnr, antnr, antd, antn, uppd);
    }

    public String toString() {
        return super.toString();
    }

    public int lon(int lön) {
        return 5000+lön;
    }
}

class Manadlöner{
    public static void main(String[] args) {
        Larare larare = new Larare("Chaliawsson", "Somchai", "123456789","1212","1 November 2000","Sch","Lärare");
        Chef chef = new Chef("Win", "Pablo", "123456789","1212","1 November 2010","Pwin","Chef");
        AdmArbetare adm = new AdmArbetare("Karlson", "Lars", "123456789","1212","1 November 2015","Larson","Admin");
        
        Arbetare[] arbetare = {larare, chef, adm};
        
        for (int i = 0; i < arbetare.length; i++) {
            System.out.println(arbetare[i]);
            System.out.println();
        }
        
        int[] manadlön ={larare.lon(10000),chef.lon(30000),adm.lon(10000)};
        
        int sum = 0;
        for (int i = 0; i < manadlön.length; i++) {
            
            sum += manadlön[i];
            
        }
        System.out.println("Totalt månadlön i C3L är "+sum);
        
    }
}
