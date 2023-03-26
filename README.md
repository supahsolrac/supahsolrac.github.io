# HTML Analyser
## Classes
Este programa opera utilizando as seguintes classes: 
* URL 
* HttpURLConnection
* String
* Stack
## Extração do texto no HTML
Para a leitura do HTML encontrado no site é utilizado como base este codigo descrito na [documentação](https://docs.oracle.com/javase/tutorial/networking/urls/readingURL.html) do Java:

```java
import java.net.*;
import java.io.*;

public class URLReader {
    public static void main(String[] args) throws Exception {

        URL oracle = new URL("http://www.oracle.com/");
        BufferedReader in = new BufferedReader(
        new InputStreamReader(oracle.openStream()));

        String inputLine;
        while ((inputLine = in.readLine()) != null)
            System.out.println(inputLine);
        in.close();
    }
}
```
## Determinação do resultado
Para descobrir qual é o texto no maior nivel de profundidade foi utilizado uma classe para guardar as tags de aberturas:
```java
class Tag{
	int depth;//nivel de profundidade
	String name;
	public Tag(int d,String n)
	{
		depth=d;
		name=n;
	}
	public int getDepth(){return depth;}
	public String getName(){return name;}
}
```
Com apoio de uma pilha de tags é determinado a profundidade de uma linha de texto e tambem se o HTML esta formatado corretamente.
