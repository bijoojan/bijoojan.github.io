---
layout: single
permalink: /contact/
author_profile: false
---

<center><font size="+3">Talk to us today about your upcoming projects or an estimate!</font> </center> 

<hr>



<font size="+2"><b>Telephone:</b> (562) 810-5051 </font><br> 

<font size="+2"><b>Email:</b> bijantavakoli54@gmail.com </font>	


<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Email Form</title>
</head>
<body>

<form id="emailForm">
    <label for="subject">Subject:</label>
    <input type="text" id="subject" name="subject" required>

    <label for="message">Message:</label>
    <textarea id="message" name="message" required></textarea>

    <button type="submit">Send Email</button>
</form>

<script>
    document.getElementById('emailForm').addEventListener('submit', function(event) {
        event.preventDefault();

        var subject = document.getElementById('subject').value;
        var message = document.getElementById('message').value;

        fetch('/send-email', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({
                subject: subject,
                message: message
            })
        }).then(response => response.json()).then(data => {
            alert(data.message);
        });
    });
</script>

</body>
</html>



