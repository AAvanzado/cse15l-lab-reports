# Part 1
StringServer Code:
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String fullString = "";

    public String handleRequest(URI url) {
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                fullString += (parameters[1] + "\n");
                return fullString;
            }
            return "Invalid URL for adding message!";
        }
        else{
            return "404 Not Found!";
        }
    }         
}

class StringServer  {
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
![Image](StringServerTest1.PNG)
 * Both the `main()` method and `handleRequest` method are called.
 * For `main()` the relevent argument is `String[] args` as `args[0]` which equals `7777` contains the port number of the webserver.
 * For `handleRequest()` the relevent arguement to this method is `URI url` which is `"http://localhost:7777/add-message?s=First%20Test"`, the entire url of the webserver.
 * As for relevent fields of the class `String fullString` which is now `"First Test" + \n`, the string printed to the webserver. Another field is `String[] parameters` as `parameters[1]` contains the string `"First Test"` which was inputted within the url as part of the query.
 * The `String fullString` field changes from an empty string to `"First Test" + \n` 

![Image](StringServerTest2.PNG)
 * Similar to the first usage of `/add-message`, both the `main()` method and `handleRequest` method are called.
 * For `main()` the relevent argument is `String[] args` as `args[0]` which equals `7777` contains the port number of the webserver.
 * For `handleRequest()` the relevent arguement to this method is `URI url` which is `"http://localhost:7777/add-message?s=Second%20Test"`, the entire url of the webserver.
 * As for relevent fields of the class `String fullString` which is now `"First Test" + \n + Second Test + \n`, the string printed to the webserver. Another field is `String[] parameters` as `parameters[1]` contains the string `"Second Test"` which was inputted within the url as part of the query.
 * The `String fullString` field changes from `"First Test" + \n` to `"First Test" + \n + Second Test + \n`.

# Part 2
## reverseInPlace() Method Bugs
 * Failure inducing input as a JUnit test
```
public void testReverseInPlace1(){
    int[] input1 = {1,2,3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{3,2,1}, input1);
}
```
 * An input that doesn't induce a failure as a JUnit test
```
public void testReverseInPlace1(){
    int[] input1 = {1,1,1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{1,1,1}, input1);
```
 * The symptom, as the output of running the tests
 
