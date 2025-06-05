# VAS integration example

This demonstration (see [default.html](default.html)) illustrates how a Virtual Assistant service can seamlessly integrate into any HTML page, including the DOMINO-E User Access Service.
You can try it out online [here](https://va.tilde.com/scontent/prodk8sbotdomin0/media/staging/default.html). 

- To see how the Virtual Assistant (VA) can send commands to its hosting page, start a conversation and specify a geographical object. When the map appears in the chat window, click the "Expand" button to open it in the hosting page.

- To see how information can be sent from the hosting page to the VA, enter some text into the input field on the hosting page and click the "Submit" button. The text will be sent to the VA and displayed in the chat.

## How to integrate a Virtual Assistant into an HTML page
First, integrate the Virtual Assistant JavaScript into the webpage.
```html
<script crossorigin="anonymous" src="https://va.tilde.com/api/prodk8sbotdomin0/media/staging/webchat.js" defer>
</script>
```
Secondly, include a placeholder indicating the location for embedding the webchat within the webpage.
```html
    <div id="webchat">
        Webchat Placeholder
    </div>
```
## How to send information from the page to the Virtual Assistant
A JavaScript function named `command_from_page_to_bot` is established for dispatching information from the page to the Virtual Assistant. 
For instance, if a user enters data into a form, you can transmit this data to the virtual assistant as text upon the submission of the form by the user.
```html
   <script>
        function handleSubmit(event) {
            event.preventDefault();
            const inputText = document.getElementById('textInput').value;
            command_from_page_to_bot('command 1: ' + inputText);
        }

        const form = document.getElementById('myForm');
        form.addEventListener('submit', handleSubmit);
    </script>
```
## How to send information from the Virtual Assistant to page
A JavaScript function called `command_from_bot_to_page` is set up to send information from the Virtual Assistant to the page. This information can be utilized if you want the Virtual Assistant to notify the page about an event or perform an action on the page. In such cases, the Virtual Assistant generates a specific message containing instructions for the page. Subsequently, the `command_from_bot_to_page` function on the page is invoked to manage the message from the Virtual Assistant. The following example demonstrates how to handle messages from the Virtual Assistant. The single message handling function is capable of managing multiple diverse notifications.
```html
    <script>
        function command_from_bot_to_page(command) {
            if (command == "zoomin") {
                ...
            }
            else if (command == "zoomout") {
                ...
            }
            else if (command == "insert_map") {
                // add a code that inserts a map in the page
                ...
            }
            else if (command.startsWith("moveto:")) {
                ...
            }
        }
    </script>
```
