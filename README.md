# HTML Analyser
## Classes
Este programa opera utilizando as seguintes classes: 
* URL 
* HttpURLConnection
* Stack <p>
## Extração do texto no HTML
Para a leitura do HTML encontrado no site é utilizado este metodo descrito em um [site](https://docs.oracle.com/javase/tutorial/networking/urls/readingURL.html) da Oracle:
<p>
~~~
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