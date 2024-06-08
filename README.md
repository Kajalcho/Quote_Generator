Random Quote Generator
@Created By: 
Name: kajal kumari
Email: kajal143698@gmail.com
🚀 Overview
This project is a simple Random Quote Generator web application. It displays a random quote every time the user clicks the "New Quote" button. The application includes features to copy the quote, share it on Twitter, and hear it through a text-to-speech feature.

📁 Project Structure
index.html: The main HTML file that structures the webpage.
style.css: The CSS file that styles the webpage.
script.js: The JavaScript file that adds functionality to the webpage.
📄 HTML Structure
The HTML file provides the basic structure of the web application. It includes a header, a content section for displaying quotes, and buttons for interaction.

Key Sections
Header: Displays the title of the application.

<header>Quote of the Day</header>
Content: Contains the quote and the author.

<div class="content">
    <div class="quote-area">
        <i class="fas fa-quote-left"></i>
        <p class="quote">"Embrace the beauty of uncertainty, for within its mystery lies the potential for endless discovery."</p>
        <i class="fas fa-quote-right"></i>
    </div>
    <div class="author">
        <span>__</span>
        <span class="name">My quotes</span>
    </div>
</div>
Buttons: Contains buttons for new quote, sound, copy, and Twitter share features.

<div class="buttons">
    <div class="features">
        <ul>
            <li class="sound"><i class="fas fa-volume-up"></i></li>
            <li class="copy"><i class="fas fa-copy"></i></li>
            <li class="twitter"><i class="fab fa-twitter"></i></li>
        </ul>
        <button>New Quote</button>
    </div>
</div>
🎨 CSS Styling
The style.css file contains styles to make the application visually appealing.

Basic Styles: Set up the basic styles for the entire document.

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
}

body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f0f0f0;
}

.wrapper {
    background: #fff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
Header: Styles for the header section.

header {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 20px;
    text-align: center;
}
Quote Area: Styles for the quote display area.

.quote-area {
    position: relative;
    font-size: 18px;
    line-height: 1.6;
    margin-bottom: 20px;
}

.quote-area i {
    position: absolute;
    font-size: 24px;
    color: #333;
}

.fa-quote-left {
    top: -10px;
    left: -10px;
}

.fa-quote-right {
    bottom: -10px;
    right: -10px;
}
Author: Styles for the author section.

.author {
    text-align: right;
    font-size: 16px;
    color: #555;
}

.author .name {
    font-weight: bold;
}
Buttons: Styles for the buttons section.

.buttons {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.features ul {
    display: flex;
    list-style: none;
}

.features li {
    margin-right: 10px;
    cursor: pointer;
}

.features button {
    background: #333;
    color: #fff;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
    transition: background 0.3s;
}

.features button:hover {
    background: #555;
}
🚀 JavaScript Functionality
The script.js file provides the functionality for generating new quotes, copying quotes to the clipboard, sharing quotes on Twitter, and text-to-speech feature.

document.addEventListener("DOMContentLoaded", () => {
    const newQuoteBtn = document.querySelector("button");
    const quoteText = document.querySelector(".quote");
    const authorText = document.querySelector(".name");
    const soundBtn = document.querySelector(".sound");
    const copyBtn = document.querySelector(".copy");
    const twitterBtn = document.querySelector(".twitter");

    const quotes = [
        {
            quote: "Embrace the beauty of uncertainty, for within its mystery lies the potential for endless discovery.",
            author: "Unknown"
        },
        // Add more quotes here
    ];

    function getRandomQuote() {
        const randomIndex = Math.floor(Math.random() * quotes.length);
        return quotes[randomIndex];
    }

    function displayQuote() {
        const randomQuote = getRandomQuote();
        quoteText.textContent = `"${randomQuote.quote}"`;
        authorText.textContent = randomQuote.author;
    }

    newQuoteBtn.addEventListener("click", displayQuote);

    soundBtn.addEventListener("click", () => {
        const utterance = new SpeechSynthesisUtterance(`${quoteText.textContent} by ${authorText.textContent}`);
        speechSynthesis.speak(utterance);
    });

    copyBtn.addEventListener("click", () => {
        navigator.clipboard.writeText(quoteText.textContent);
    });

    twitterBtn.addEventListener("click", () => {
        const tweetUrl = `https://twitter.com/intent/tweet?text=${quoteText.textContent} - ${authorText.textContent}`;
        window.open(tweetUrl, "_blank");
    });

    // Display a quote on load
    displayQuote();
});
Conclusion
This Random Quote Generator project provides a simple yet functional web application to display random quotes. It demonstrates the use of HTML for structure, CSS for styling, and JavaScript for interactivity. This project is an excellent example for beginners to understand how to build interactive web applications.
