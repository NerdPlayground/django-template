# Django Application Template
This template is used to setup the base for your Django application. It comes with the following;
- Packages
    - Python Decouple - which connects the environment variables to the application
    - Psycopg - PostgreSQL database adapter for Python
- Configured settings for;
    - Environment variables - SECRET_KEY and DEBUG
    - Database
    - Templates
    - Static files
- Base frontend which includes;
    - the home page
    - styles in SASS along which a list of helpful SASS functions

## Implementing the template
1. Setup your virtual environment
    - Create the virtual environment; `virtualenv <virtual environment name>`
    - Activate the environment; `source <virtual environment name>/Scripts/activate`
    - To deactivate the environment; `deactivate`
2. Add your environment variables with the following command - this will add SECRET_KEY and DEBUG in the .env file;
    ```PowerShell
    python -c "import secrets; write_to=open('./application/.env','w',encoding='utf-8'); write_to.write('SECRET_KEY='+secrets.token_urlsafe()+'\n'+'DEBUG=True')"
    ```
3. Setup your Database using [pgAdmin4](https://www.postgresql.org/download/);
    - Open the application and click on Servers
    - Select a PostgreSQL server and create a database in it
    - In your .env file, create the following variables for your database - retrieve `USER`, `HOST` and `PORT` from the server properties in the **Connection** tab
        ```
        USER=your_db_user
        PASSWORD=your_password
        HOST=your_host
        PORT=your_port
        NAME=your_db_name
        ```
4. Build the application; `bash build.sh` which will install the application packages, collect static files and submit your database to the server
5. Run your application; `python manage.py runserver`
