# Lab Report 2
This report first shows the code for the ChatServer.java file 

## Code for the `ChatServer` file:
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a string that will be manipulated by
    // various requests.
    String retVal = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("&");
            String message = parameters[0];
            String user = parameters[1];
            String[] messageArr = message.split("=");
            String[] userArr = user.split("=");
            String messageOut = messageArr[1];
            String userOut = userArr[1];

            retVal = retVal + String.format(userOut + ": " + messageOut + "\n");
            return retVal;
        } 
        return retVal;
    }
}


class ChatServer {
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

---
---

## Example 1
![Image](ss1.png)

* The HandleRequest and main method from the code is called.


---

## Example 2
![Image](ss2.png)
