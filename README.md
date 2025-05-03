# Expense Tracker 💰 by Deeha Giri (20231BCI0016) :

A modern web application for tracking personal expenses built with Flask, SQLite, and a clean, responsive UI.

## Features

- 🔐 User Authentication (Signup/Login)
- 💸 Add, Edit, and Delete Expenses
- 📊 Expense Statistics and Analytics
- 📅 Date-based Expense Tracking
- 💰 Category-based Expense Management
- 📱 Responsive Design
- 🔄 Real-time Updates

## Tech Stack

- **Backend**: Flask (Python)
- **Database**: SQLite
- **Frontend**: HTML, CSS, JavaScript
- **Containerization**: Docker
- **Authentication**: Flask-Login
- **CI/CD**: GitHub Actions

## Prerequisites

- Python 3.9 or higher
- Docker (for containerized deployment)
- Git (for version control)

## Installation & Setup

### Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/Di-e-fied/student-expense-tracker.git
   cd student-expense-tracker
   ```

2. Create and activate virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Set up environment variables:
   ```bash
   export FLASK_APP=app
   export FLASK_ENV=development
   export SECRET_KEY=your-secret-key
   ```

5. Run the application:
   ```bash
   flask run
   ```

### Docker Deployment

1. Build the Docker image:
   ```bash
   docker build -t expense-tracker .
   ```

2. Run the container:
   ```bash
   docker run -p 5000:5000 -v $(pwd):/app -v $(pwd)/instance:/app/instance expense-tracker
   ```

3. Access the application at `http://localhost:5000`

## Docker Image

The application is available as a Docker image:

```bash
docker pull sujalgp/expense-tracker:latest
docker run -p 5000:5000 sujalgp/expense-tracker:latest
```

## CI/CD Pipeline

This project uses GitHub Actions for continuous integration and deployment. The workflow is defined in `.github/workflows/ci-cd.yml`.

### Workflow Features

- 🔄 Automatic builds on push to main branch
- 🐳 Docker image building and pushing
- 🏷️ Multiple tags for version tracking
- ⚡ Layer caching for faster builds

### How it Works

1. **Trigger**: The workflow runs on:
   - Push to main branch
   - Pull requests to main branch

2. **Build Process**:
   - Uses Docker Buildx for efficient builds
   - Implements layer caching for faster builds
   - Creates two tags for each build:
     - `latest`
     - Git commit SHA

3. **Docker Hub Integration**:
   - Automatically pushes to Docker Hub
   - Uses secure secrets for authentication
   - Maintains version history

### Setup Requirements

To use the CI/CD pipeline, you need to set up the following secrets in your GitHub repository:

1. Go to repository Settings > Secrets and variables > Actions
2. Add the following secrets:
   - `DOCKERHUB_USERNAME`: Your Docker Hub username
   - `DOCKERHUB_TOKEN`: Your Docker Hub access token

### Manual Trigger

You can also manually trigger the workflow:
1. Go to the Actions tab in your repository
2. Select the "CI/CD Pipeline" workflow
3. Click "Run workflow"

## Project Structure

```
expense-tracker/
├── app/
│   ├── static/
│   │   └── style.css
│   ├── templates/
│   │   ├── index.html
│   │   ├── login.html
│   │   └── signup.html
│   ├── __init__.py
│   ├── models.py
│   ├── routes.py
│   └── auth.py
├── instance/
│   └── expenses.db
├── .github/
│   └── workflows/
│       └── ci-cd.yml
├── Dockerfile
├── requirements.txt
└── README.md
```

## API Endpoints

- `POST /signup` - User registration
- `POST /login` - User authentication
- `GET /logout` - User logout
- `GET /` - Dashboard/Home page
- `POST /add_expense` - Add new expense
- `PUT /update_expense/<id>` - Update existing expense
- `DELETE /delete_expense/<id>` - Delete expense

## Features in Detail

### User Authentication
- Secure user registration and login
- Password hashing for security
- Session management

### Expense Management
- Add expenses with amount, category, and date
- Edit existing expenses
- Delete expenses
- View expense history

### Analytics
- Monthly expense summary
- Category-wise expense breakdown
- Visual representation of spending patterns

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Author

Deeha Giri

## Acknowledgments

- Flask Documentation
- SQLite Documentation
- Docker Documentation
- GitHub Actions Documentation # student-expense-tracker
# student-expense-tracker
# student-expense-tracker
# student-expense-tracker
