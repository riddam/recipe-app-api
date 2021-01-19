
# Recipe APIs
This project provides public and private APIs for recipes,
ingredients and tags endpoints. Client can perform CRUD operations on resource based on authentication and authorization

API URL:     
base: `http://127.0.0.1:8000/`    
endpoints:

    admin/
    api/user/ create/ [name='create']
    api/user/ token/ [name='token']
    api/user/ me/ [name='me']
    api/recipe/



## Prerequisite
### Application with Docker:
 - [docker](https://docs.docker.com/engine/install/)

### Application without Docker:
Install following application as per your operating system
 - [postgres database](https://www.postgresql.org/download/)
 - [python3](https://www.python.org/downloads/)
 - [virtualenv](https://virtualenv.pypa.io/en/latest/index.html)
    or
    [pipenv](https://pipenv.pypa.io/en/latest/)


## Installation
1. Make the directory and move to created directory:  
`mkdir recipe_project`  
`cd recipe_project`   

2. Clone the repository    
`git clone git@github.com:riddam/recipe-app-api.git`

### Application with Docker:
3. Change to the directory where docker files are present. Build the dockerfile and run docker container  
`docker build -t recipe-image .`   
or build docker compose file:

  `docker-compose build `

4. Run the application using following command:     
  `docker-compose  up`

### Application without Docker:

3. Create the virtual environment      
  `virtualenv -p python3 venv` or `pipenv --three`    
  and activate it:
  `source venv/bin/activate` or `pipenv shell`

4. Install project requirement using following command:     
  `pip install -r /requirements.txt`

5. Update database URI and credentials in app/app/settings.py file as per your db configuration

6. Enter following command in command prompt(or terminal) where manage.py is located
  `python manage.py migrate`


## Tests
### Application with Docker:
Run the unit test and coding convention check using following command    
  `docker-compose run --rm app sh -c "python manage.py test && flake8"`

### Application without Docker:
Run following command in command prompt(or terminal) where manage.py is located       
  `python manage.py test && flake8`

## Usage
- Run the application using following command for docker:     
  `docker-compose  up`      

  Otherwise run the application using below command:      
  `python manage.py runserver`

- Open web browser and type server URL with target endpoint    
  Example:
  create a new user     
    `http://127.0.0.1:8000/api/user/create/`    
  Retrieve token using    
    `http://127.0.0.1:8000/api/user/token/`

## License
  Distributed under the MIT License. See LICENSE for more information.
