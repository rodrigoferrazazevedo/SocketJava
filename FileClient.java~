import java.io.*;
import java.io.DataOutputStream;
import java.io.FileInputStream;
import java.io.IOException;
import java.net.Socket;

public class FileClient {
	
	private Socket s;
	
	public FileClient(String host, int port, String file) {
		try {
			s = new Socket(host, port);
			sendFile(file);
		} catch (Exception e) {
			e.printStackTrace();
		}	
	}
	
	public void sendFile(String file) throws IOException {
		DataOutputStream dos = new DataOutputStream(s.getOutputStream());
		FileInputStream fis = new FileInputStream(file);
		byte[] buffer = new byte[4096];
		
		while (fis.read(buffer) > 0) {
			dos.write(buffer);
		}
		
		fis.close();
		dos.close();	
	}
	
	public static void main(String[] args)  throws IOException {
	  while(true){		
		System.out.println("Informe a operação:");
		System.out.println("1. Enviar Arquivo");
		System.out.println("2. Receber Arquivo");

		BufferedReader brEntrada = new BufferedReader(new InputStreamReader(System.in));		
		String strOperacao = brEntrada.readLine();
		
		System.out.println("");
		System.out.println("Operação: " + strOperacao);	
		
		if(strOperacao.contains("1")){
			System.out.println("Enviando arquivo...");
			FileClient fc = new FileClient("localhost", 1988, "cat.jpg");
		}else if(strOperacao.contains("2")){
			System.out.println("Recebendo arquivo...");
		}else{
			System.out.println("Operacao invalida");
		}

		System.out.println("");
		System.out.println("Recarregando menu...");
		System.out.println("");
	  }

	}

}
