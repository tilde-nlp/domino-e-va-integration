# VAS integration exaple

This demonstration illustrates how a Virtual Assistant service can seamlessly integrate into any HTML page, including the DOMINO-E User Access Service.

## How to integrate a Virtual Assistant into an HTML page
First, integrate the Virtual Assistant JavaScript into the webpage.
```html:
<script crossorigin="anonymous" src="https://va.tilde.com/api/prodk8sbotdomin0/media/staging/webchat.js" async defer>
</script>
```
Secondly, include a placeholder indicating the location for embedding the webchat within the webpage.
```html:
    <div id="webchat">
        Webchat Placeholder
    </div>
```
## How to send information from the page to the Virtual Assistant
A JavaScript function named `command_from_page_to_bot` is established for dispatching information from the page to the Virtual Assistant. 
For instance, if a user enters data into a form, you can transmit this data to the virtual assistant as text upon the submission of the form by the user.
```html:
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
