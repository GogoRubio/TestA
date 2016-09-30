# TestA

public class Auto {
	private String modelo;
	private String marca;
	private String color;
	protected double precio;
	private double descuento;
	private int puertas;
	
	
	public Auto(double Precio){
		this.precio=Precio;
	}
	public String getmodelo(){
	    return modelo; 
	}

	public void setmodelo(String setmodelo){
	    this.modelo=setmodelo;

	}

	public String getmarca(){
	    return marca;
	}

	public void setmarca(String setmarca){
	    this.marca=setmarca;

	}

	public String getcolor(){
	    return color;
	}

	public void setcolor(String setcolor){
	    this.color=setcolor;

	}
	
	public double getprecio(){
	    return precio;
	}

	public void setprecio(double setprecio){
	    this.precio=setprecio;

	}
	
	
	public int getpuertas(){
	    return puertas; 
	}

	public void setpuertas(int setpuertas){
	    this.puertas=setpuertas;
}
	
	
	

	public double descuento(double getdescuento){
	    this.descuento=getdescuento;
	    return descuento;


	}

	public double preciot(double setprecio){
	    this.precio=setprecio;
	    if (precio>10 && precio<20){
	        return precio;
	    }else {
	        System.out.println("no es adecuado el precio");
	    }

	    //precio=(setprecio-(setprecio*descuento));
	    System.out.println("el precio del taco es:"+precio);
	    return precio;


	}
	}
  
  
  public class Usado extends Auto {

	private double preciou;
	
	public Usado(double precio){
		super(precio);
	}
	
	public double descuentousado(double setdescuento){
	    this.preciou=setdescuento;
	    preciou=precio-(precio*setdescuento);
	    return preciou; 
	}
	
	public double compra(double setcompra){
	    this.preciou=setcompra;
	    preciou=precio*setcompra;
	    return preciou; 
	}
	
}

public class Seminuevo extends Auto {
	public Seminuevo(double Precio) {
		super(Precio);
		// TODO Auto-generated constructor stub
	}

private double preciou;
private int puertas;
private String seguro;
	
	public double descuentosemi(double setdescuento){
		this.preciou=setdescuento;
	    preciou=precio+(precio*setdescuento);
	    return preciou; 
	}
	
	
	public double compra(double setcompra){
	    this.preciou=setcompra;
	    preciou=precio-(precio*setcompra);
	    return preciou; 
	}
	
	public String getseguro(){
	    return seguro; 
	}
	public String setseguro(String setseguro){
		this.seguro=setseguro;
		if (setseguro=="si"){
			System.out.println("Si cuentas con seguro con un costo de $25000");
			
		}return setseguro;
	}
	
	public int getpuertas(){
	    return puertas; 
	}

	public void setpuertas(int setpuertas){
	    this.puertas=setpuertas;
}
}

public class Nuevo extends Auto {
	public Nuevo(double Precio) {
		super(Precio);
		// TODO Auto-generated constructor stub
	}

private double preciou;
	
	public double aumentonuevo(double setaumento){
		this.preciou=setaumento;
	    preciou=precio+(precio*setaumento);
	    return preciou; 
	}

	public double compra(double setcompra){
	    this.preciou=setcompra;
	    double setdescuento=.1225;
	    if(setcompra>5.0){
	    	preciou=precio-(precio*setdescuento);
	    	preciou=precio*setcompra;
	    	
	    }
	    return preciou; 
	}
	
	
}


public class App {
	public static void main(String[] args) {

		Usado a =new Usado(0);
		a.setmodelo("focus");
		a.setmarca("chrevolet");
		a.setcolor("rojo");
		a.setprecio(100000.00);
		a.descuentousado(.35);
		a.compra(10);
		System.out.println("El modelo es: "+ a.getmodelo()+"\nLa marca es: "+a.getmarca()
				            +"\nEl color es: "+a.getcolor()+"\nEl precio es: "
		                   +a.getprecio()+"\nEl descuento por usado es: "+a.descuentousado(.35)
		                   +"\nEl precio total de su compra es de: "+a.compra(10));
		
		Seminuevo s= new Seminuevo(0);
		s.setmodelo("corolla");
		s.setmarca("toyota");
		s.setcolor("azul");
		s.setprecio(100000.00);
		s.setpuertas(4); 
		//s.compra(12);
		System.out.println("\nEl modelo es: "+ s.getmodelo()+"\nLa marca es: "+s.getmarca()
	            +"\nEl color es: "+s.getcolor()+"\nEl precio es: "
               +s.getprecio()+"\nNumero de Puertas: "+s.getpuertas() +"\nElcosto del seguro es de 250000");
		
		Nuevo n= new Nuevo(0);
		n.setmodelo("Volkswagen");
		n.setmarca("Escarabajo");
		n.setcolor("Blanco");
		n.setprecio(100000.00);
		n.setpuertas(2); 
		s.compra(12.0);
		System.out.println("\nEl modelo es: "+ n.getmodelo()+"\nLa marca es: "+n.getmarca()
	            +"\nEl color es: "+n.getcolor()+"\nEl precio es: "
               +n.getprecio()+"\nNumero de Puertas: "+n.getpuertas() +"\nEl precio con el aumeto es: "+n.aumentonuevo(.2275)
               +"\nEl precio total de su compra es:"+s.compra(12.0));
		
			
		
		
			
		
	}
}


