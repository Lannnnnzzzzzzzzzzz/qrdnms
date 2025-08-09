# QRIS Dynamic Generator
[![Ask DeepWiki](https://devin.ai/assets/askdeepwiki.png)](https://deepwiki.com/Lannnnnzzzzzzzzzzz/qrdnms)

A web application to convert a static QRIS (Quick Response Code Indonesian Standard) into a dynamic one by specifying a payment amount and an optional transaction fee. This tool is built with React and Vite, runs entirely on the client-side, and provides a simple, mobile-friendly interface for generating payment QR codes on the fly.

## Features

- **Dynamic QRIS Generation**: Converts any static QRIS into a dynamic QRIS with a specific transaction amount.
- **Image Upload**: Scan a static QRIS code directly by uploading an image file (PNG, JPEG, etc.).
- **Fee Calculation**: Add a transaction fee, either as a fixed Rupiah amount or a percentage of the total.
- **Payment History**: Automatically saves the last 5 successfully scanned QRIS codes for quick reuse.
- **Client-Side Processing**: All QRIS parsing, generation, and validation happen in the browser. No data is sent to a server.
- **Responsive UI**: A clean interface that works seamlessly on both desktop and mobile devices.

## How It Works

The application follows the QRIS standard to inject transaction-specific data into a static QRIS string:

1.  **Input**: Takes a static QRIS string, either from an uploaded image or from saved history.
2.  **Modification**:
    *   It changes the Point of Initiation method from "static" (`11`) to "dynamic" (`12`).
    *   It inserts the transaction amount using **Tag `54`**.
    *   If a fee is provided, it inserts the fee information using **Tag `55`**.
3.  **Checksum Recalculation**: It recalculates the **CRC16** checksum for the newly formed dynamic QRIS string.
4.  **Output**: Generates a new QR code image from the final dynamic QRIS string, ready to be scanned for payment.

## Technologies Used

-   **Frontend**: React, TypeScript
-   **Build Tool**: Vite
-   **Styling**: Tailwind CSS
-   **QR Code Decoding**: [jsQR](https://github.com/cozmo/jsQR)
-   **QR Code Generation**: [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator)

## Getting Started

To run this project locally, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Lannnnnzzzzzzzzzzz/qrdnms.git
    cd qrdnms
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Run the development server:**
    ```bash
    npm run dev
    ```

4.  Open your browser and navigate to `http://localhost:5173` (or the URL provided by Vite).

## License

This project is licensed under the **GNU General Public License v3.0**. See the [LICENSE](LICENSE) file for more details.

## Credits

-   Code by Lann Zephry
