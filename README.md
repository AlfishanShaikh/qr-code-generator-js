# QR Code Generator (js)

A lightweight, browser-based QR code generator built with HTML, CSS, and JavaScript. Input any text or URL to instantly generate a QR code that can be viewed and downloaded — no backend needed.

## Badges

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Table of Contents

- [Key Features](#key-features)

- [Architecture Overview](#architecture-overview)

- [Tech Stack](#tech-stack)

- [Getting Started](#getting-started)

  - [Prerequisites](#prerequisites)

  - [Installation](#installation)

- [Configuration](#configuration)

- [Usage](#usage)

- [Project Structure](#project-structure)

- [Roadmap](#roadmap)

- [Contributing](#contributing)

- [Testing](#testing)

- [License](#license)

- [Acknowledgements](#acknowledgements)

## Key Features

-   **Instant QR Code Generation**: Quickly generate QR codes from any text or URL input.

-   **Browser-Based**: Runs entirely in the client's browser, requiring no server-side processing.

-   **Lightweight**: Minimal dependencies for a fast and responsive user experience.

-   **External API Integration**: Utilizes a public API for reliable QR code image generation.

-   **Error Handling**: Provides visual feedback for empty input fields.

## Architecture Overview

This project is a single-page, client-side web application. It follows a simple architecture where HTML provides the structure, CSS handles the styling, and JavaScript manages the application logic. When a user inputs text or a URL and triggers the generation, the JavaScript code constructs a URL for an external QR code generation API (`https://api.qrserver.com/v1/create-qr-code/`) and dynamically updates an `<img>` tag's `src` attribute with the generated QR code image. There is no backend component; all operations, including QR code image fetching, occur directly in the user's browser.

## Tech Stack

| Area | Tool | Version |
|---|---|---|
|---|---|---|
| Frontend | HTML | N/A |
| Frontend | CSS | N/A |
|---|---|---|
| Frontend | JavaScript | N/A |
| API | QR Server API | v1 |
|---|---|---|



## Getting Started

Follow these instructions to get a copy of the project up and running on your local machine.

### Prerequisites

You only need a modern web browser to run this application.

### Installation

1.  **Clone the repository**:

```bash
git clone https://github.com/AlfishanShaikh/qr-code-generator-js.git

```
2.  **Navigate to the project directory**:

```bash
cd qr-code-generator-js

```
3.  **Open the application**:
    Simply open the `index.html` file in your preferred web browser.

```bash
open index.html # On macOS

start index.html # On Windows
    xdg-open index.html # On Linux

```
## Configuration

This project does not use environment variables for configuration. The QR code generation API endpoint is currently hardcoded within `script.js`.

| ENV | Description | Example |
|---|---|---|
|---|---|---|
| N/A | API endpoint for QR code generation (currently hardcoded in `script.js`) | `https://api.qrserver.com/v1/create-qr-code/` |



## Usage

1.  Open the `index.html` file in your web browser.
2.  Locate the input field labeled "Enter text or URL".
3.  Type or paste the text or URL you wish to convert into a QR code.
4.  Click the "Generate QR Code" button.
5.  The generated QR code will appear below the input field.

Here's the core JavaScript logic for generating the QR code:

```javascript
// script.js

let imgBox = document.getElementById("imgBox");
let qrImage = document.getElementById("qrImage");

let qrText = document.getElementById("qrText");

function generateQR() {

if (qrText.value.length > 0) {
qrImage.src =

"https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=" + qrText.value;
imgBox.classList.add("show-img");

} else {
qrText.classList.add("error");

setTimeout(() => {
qrText.classList.remove("error");

},1000)
}

}

```
## Project Structure

```
.

├── index.html         # Main HTML file (assumed)
├── style.css          # Stylesheet for the application (assumed)

├── script.js          # Core JavaScript logic
└── README.md          # Project README file

```
## Roadmap

-   [ ] Implement a download button for the generated QR code image.

-   [ ] Add options for customizing QR code size and error correction level.

-   [ ] Improve input validation and user feedback for various scenarios.

-   [ ] Enhance UI/UX with a more modern design.

-   [ ] Explore client-side QR code generation to remove external API dependency.

## Contributing

Contributions are welcome! If you have suggestions for improvements, bug fixes, or new features, please feel free to:

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/YourFeature`).
3.  Make your changes.
4.  Commit your changes (`git commit -m 'Add some feature'`).
5.  Push to the branch (`git push origin feature/YourFeature`).
6.  Open a Pull Request.

Please ensure your code adheres to the existing style and conventions.

## Testing

This project currently does not include automated tests. Functionality can be manually verified by opening `index.html` in a web browser and interacting with the input and generate button.

## License

This project is licensed under the MIT License - see the `LICENSE` file for details (a `LICENSE` file containing the MIT license text should be created in the root of the repository).

## Acknowledgements

-   [QR Server API](https://www.qrserver.com/) for providing a free and reliable API for QR code generation.
