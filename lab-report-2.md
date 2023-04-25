## **Lab Report 2 - Servers and Bugs**

### Part 1: Creating a Web Server

Write a web server called StringServer that supports the path and behavior described below. It should keep track of a 
single string that gets added to by incoming requests. The requests should like th

`/add-message?s=<string>`


The following is my code for StringServer:

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // A string that will be manipulated by various requests.
    String output = "";

    public String handleRequest(URI url) {
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                output += parameters[1] + "\n";
            }
        }
        return output;
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

After writing the code for StringServer, I altered the path to check that code produced the expected output.



