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
