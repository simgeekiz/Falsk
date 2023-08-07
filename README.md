
## Flask API Example: Building a Simple API with GitHub Actions
### TODO
- When I am using only github actions It seems to be running somewhere However I do not know how I can reach the flask API
- I tried to reach it inside the CI/CD however the server is not returning something.

### Installation
Follow these steps to install and run the project on your local machine.

### Prerequisites

- Python 3.x (Install from [python.org](https://www.python.org/downloads/))
- Git (Install from [git-scm.com](https://git-scm.com/downloads))

### Clone the Repository

1. Open your terminal or command prompt.
2. Navigate to the directory where you want to clone the repository.
3. Run the following command to clone the repository:

  ```bash
  $ git clone https://github.com/simgeekiz/Falsk.git
  ```

### Set Up Virtual Environment (Optional but Recommended)

1. Navigate to the project directory:

  ```bash
  $ cd your-repo
  ```

2. Create a virtual environment and then activate it;

  - On macOS and Linux:
  ```bash
  $ python3 -m venv .env
  $ source .env/bin/activate
  ```

  - On Windows:
  ```bash
  $ python -m venv .env
  $ .\.env\Scripts\activate
  ```

### Install Dependencies

  ```bash
  pip install -r requirements.txt
  ```

  Normally we would have multiple dependencies but for this example, 
  We are only using flask
  
  ```bash
  pip install flask
  ```

### Run the Project

1. Start the Flask application:

  ```bash
  flask --app hello run
  ```

  or add to main.py
  ```
  if __name__ == '__main__':
    app.run(debug=False)
  ```
  Then run;
  ```bash
  python main.py
  ```

2. Open your web browser and navigate to http://localhost:5000 to access the application.

### Deactivate Virtual Environment

When you're done using the project, deactivate the virtual environment:
  ```bash
  deactivate
  ```

### Troubleshooting

If you encounter any issues during the installation process, feel free to open an issue for assistance.