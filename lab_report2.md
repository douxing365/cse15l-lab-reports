## Lab report 2 
# Part 1: Chat Server 
**Code for the ChatServer**
```
import java.io.IOException;
import java.net.URI;
import java.net.URLDecoder;
import java.nio.charset.StandardCharsets;

class Handler implements URLHandler {
    private String chatHistory = "";

    @Override
    public String handleRequest(URI url) {
        if ("/add-message".equals(url.getPath())) {
            String query = url.getQuery();
            if (query == null) {
                return "Query string is missing!";
            }

            String[] queryParams = query.split("&");
            String user = null;
            String message = null;

            for (String param : queryParams) {
                String[] keyValue = param.split("=");
                if ("user".equals(keyValue[0]) && keyValue.length > 1) {
                    user = URLDecoder.decode(keyValue[1], StandardCharsets.UTF_8);
                } else if ("s".equals(keyValue[0]) && keyValue.length > 1) {
                    message = URLDecoder.decode(keyValue[1], StandardCharsets.UTF_8);
                }
            }

            if (user != null && message != null) {
                chatHistory += user + ": " + message + "\n";
                return chatHistory;
            } else {
                return "Invalid or incomplete parameters!";
            }
        } 
        else if ("/".equals(url.getPath())) {
            // Handling the root path
            return "Welcome to the Chat Server! Use /add-message to add messages.";
        }
        else {
            return "404 Not Found: The requested URL " + url.getPath() + " was not found on this server.";
        }
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
**Screenshots of using `/add-message`:**<br />
`/add-message?s=Hello&user=jpolitz`
![Image](screenshotofadd1.png)<br />
`/add-message?s=How are you&user=yash`
![Image](screenshotofadd2.png)<br />


