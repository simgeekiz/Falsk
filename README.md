
## Flask API Example: Building a Simple API with GitHub Actions using Heroku Hosting Services

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

### Prepare a Flask application for Heroku
1. Create the Procfile
  ```bash
    web: gunicorn wsgi:app
  ```
  or
  ```bash
    web: gunicorn app:app
  ```
  Note: You can store the code below in wsgi.py or you can store it in app.py with the rest of the code. Just update your procfile according to this. I choose to store it in app.py so in my procfile it is web: gunicorn app:app
  
  ```bash
    if __name__ == '__main__':
      app.run(host='0.0.0.0')
  ```
  
2. Create the requirements.txt 
  Heroku needs requirements.txt to understand that it is a python app

  gunicorn is needed for Heroku 
  You can install it by 
  ```bash
    pip install gunicorn
  ```

  ```bash
    pip freeze > requirements.txt
  ```

3. Create the runtime.txt
  Python version os stored in runtime.txt
  You can figure out the python version by running;
  ```bash
    python --version
  ```
  then correct the version but syntax needs to be in the following format.

  ```bash
    python-3.10.6
  ```

### Set up Heroku

1. Install Heroku CLI and the login via terminal(for linux).

  ```bash
    heroku login
  ```

2. Create a Heroku app

  ```bash
    heroku create simpleflask
  ```

### Build a CI/CD pipeline with GitHub Actions

After pushing the code to the repository, the CI/CD pipeline will automatically initiate, and GitHub will take care of the subsequent processes. You can observe this by navigating to the "Actions" tab. 

Do not forget to add your private variables into secrets
e.g. secrets.HEROKU_API_KEY

### Troubleshooting

If you encounter any issues during the installation process, feel free to open an issue for assistance.

# Licence 
  MIT License: http://igliu.mit-license.org/
