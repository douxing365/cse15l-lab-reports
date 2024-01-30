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
![Image](screenshotofadd1.png)<br />
`/add-message?s=Hello&user=jpolitz`<br />
1. Which methods in your code are called?
  * `handleRequest(URI url)` in the `Handler` class
2. What are the relevant arguments to those methods, and the values of any relevant fields of the class?
  * Relevant argumentshandleRequest(URI url):
   `URI url`: This contains the URI of the request. It will have the path `/add-message` and the query              `s=Hello&user=jpolitz`.
  * Relevant Fields in `Handler` class: `private String chatHistory`
3. How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
  * Changes in `chatHistory`:Before the request `chatHistory` is an empty `string`, After processing the request with `/add-message?s=Hello&user=jpolitz` `chatHistory` will be updated to include the new message.

`/add-message?s=How are you&user=yash`
![Image](screenshotofadd2.png)<br />
1. Which methods in your code are called?
  * `handleRequest(URI url)` in the `Handler` class
2. What are the relevant arguments to those methods, and the values of any relevant fields of the class?
  * Relevant argumentshandleRequest(URI url):
   `URI url`: This contains the URI of the request. It will have the path `/add-message` and the query              `s=Hello&user=jpolitz`.
  * Relevant Fields in `Handler` class: `private String chatHistory`
3. How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
  * Changes in `chatHistory`:Before the request: `chatHistory` is whatever it was up to that point, After processing the request `chatHistory` will be updated with the new message, resulting in "yash: How are you\n" being appended to the existing `chatHistory`.
# Part 2: Setting up SSH Keys for Easy Access



