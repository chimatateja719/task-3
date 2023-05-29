<!DOCTYPE html>
<html>
<head>
    <title>Product Review</title>
    <style>
        /* CSS styles for the form */
        body {
            font-family: monospaced, sans-serif;
            margin: 0;
            padding: 20px;
            background-color:pink;
        }

        h1 {
            text-align: center;
        }

        form {
            max-width: 500px;
            margin:0 auto;
        }

        label {
            display: block;
            margin-bottom: 10px;
        }

        input[type="text"],
        input[type="number"],
        textarea {
            width: 100%;
            padding: 8px;
            margin-bottom: 15px;
            border: 1px solid black;
        }

        input[type="submit"] {
            background-color: green;
            color: white;
            padding: 10px 20px;
            border: none;
            cursor: pointer;
        }

        #response {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Product Review</h1>
    <form onsubmit="submitForm(event)">
        <label for="product_link">Product Link:</label>
        <input type="text" id="product_link" required>
        <label for="rating">Rating:</label>
        <input type="number" id="rating" min="1" max="5" required>
        <label for="review">Review:</label>
        <textarea id="review" required></textarea>
        <input type="submit" value="Submit">
    </form>
    <div id="response"></div>

    <script>
        function submitForm(event) {
            event.preventDefault();

            var productLink = document.getElementById("product_link").value;
            var rating = document.getElementById("rating").value;
            var review = document.getElementById("review").value;

            var responseText = "Thank you for your " + rating + "-star review. We're glad to hear that you found the product " + review + "!";
            document.getElementById("response").textContent = responseText;
        }
    </script>
</body>
</html>
