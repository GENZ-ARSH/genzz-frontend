# GenZZ Library

GenZZ Library is a web-based PDF library for educational resources, designed for students preparing for Board, JEE, NEET, and other exams. It features a secure access system with time-based keys for users and an admin panel for managing books. This README provides instructions to set up and run the frontend locally or deploy it to a hosting service.

## Prerequisites

Before setting up the project, ensure you have the following:

- **Node.js** (v16 or higher): Required for local development and building the project.
- **npm** or **yarn**: Package managers for installing dependencies.
- **Git**: For cloning the repository.
- **Text Editor**: VS Code or any editor for editing HTML/CSS/JS files.
- **Web Browser**: Chrome, Firefox, or any modern browser for testing.
- **Backend Access**: The backend API is hosted at `https://genzz-backend.onrender.com`. Ensure you have the API documentation or access to the backend team for endpoints like `/api/generate-key`, `/api/validate-key`, `/api/admin-login`, and `/api/books`.
- **Hosting Service Account**: Netlify, Vercel, or similar for deployment.

## Project Structure

```
genzz-library/
├── assets/
│   └── favicon.ico        # Favicon for the website
├── index.html             # Landing page for key generation
├── protected.html         # Token validation page
├── home.html              # Main library page with books
├── admin.html             # Admin panel for managing books
├── README.md              # Setup instructions (this file)
└── features.md            # Feature guide for site management
```

## Setup Instructions

### 1. Clone the Repository

Clone the project to your local machine:

```bash
git clone https://github.com/your-repo/genzz-library.git
cd genzz-library
```

*Replace `https://github.com/your-repo/genzz-library.git` with your actual repository URL.*

### 2. Install Dependencies

The frontend is a static HTML/CSS/JS project with no build dependencies, but you may need a local server for development. Install `live-server` globally for easy local testing:

```bash
npm install -g live-server
```

Alternatively, use Python's HTTP server or any other local server.

### 3. Run Locally

Start a local server to serve the HTML files:

```bash
live-server
```

This will open the project in your default browser at `http://localhost:8080`. Navigate to `index.html` to test the key generation flow.

### 4. Configure Backend API

The frontend communicates with the backend API at `https://genzz-backend.onrender.com`. Ensure the `BASE_API_URL` constant in all HTML files (`index.html`, `protected.html`, `home.html`, `admin.html`) is set correctly:

```javascript
const BASE_API_URL = 'https://genzz-backend.onrender.com';
```

If you have a custom backend URL, update this in all files.

### 5. Test Key Generation and Access

1. Open `index.html` in the browser.
2. Click "24 Hour Access" or "48 Hour Access" to generate a key.
3. The app redirects to `protected.html` for token validation.
4. If valid, it redirects to `home.html` to display the library.
5. For admin access, triple-click the footer on `index.html` or `home.html` and enter the admin password (contact the backend team for the password).

### 6. Deploy to Netlify

To deploy the frontend to Netlify:

1. **Push to GitHub**:
   - Initialize a Git repository if not already done:
     ```bash
     git init
     git add .
     git commit -m "Initial commit"
     git remote add origin https://github.com/your-repo/genzz-library.git
     git push -u origin main
     ```

2. **Create a Netlify Account**:
   - Sign up at [Netlify](https://www.netlify.com).

3. **Deploy the Site**:
   - Log in to Netlify and click "New site from Git."
   - Connect to your GitHub repository.
   - Set the build settings:
     - **Build command**: Leave blank (no build required for static HTML).
     - **Publish directory**: `.` (root directory).
   - Click "Deploy site."
   - Netlify will provide a URL (e.g., `https://your-genzz-library.netlify.app`).

4. **Custom Domain (Optional)**:
   - Configure a custom domain in Netlify's domain settings.

### 7. Troubleshooting

- **Key Generation Fails**: Check the browser console for errors. Ensure the backend API is reachable and the `BASE_API_URL` is correct.
- **Token Validation Fails**: Verify that `accessToken` and `accessTokenExpiry` are stored in `localStorage`. Check backend logs for `/api/validate-key` errors.
- **Admin Login Fails**: Ensure the correct password is used for `/api/admin-login`. Contact the backend team for assistance.
- **CORS Issues**: If API requests fail due to CORS, confirm the backend allows requests from your frontend domain.

## Contributing

To contribute to the project:

1. Fork the repository.
2. Create a feature branch:
   ```bash
   git checkout -b feature/your-feature
   ```
3. Commit changes:
   ```bash
   git commit -m "Add your feature"
   ```
4. Push to your fork:
   ```bash
   git push origin feature/your-feature
   ```
5. Open a pull request on the main repository.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For questions or support, join our Telegram channel: [Gen-Z Coders](https://t.me/genzcoders1) or contact the project maintainers.

---
*Made with ❤️ by GenZ-Coders*