 ### While there are many possible commands we can use, in practice there are six use most frequently in Django development.
 - cd (change down a directory)
 - cd .. (change up a directory)
 - ls (list files in your current directory)
 - pwd (print working directory)
 - mkdir (make directory)
 - touch (create a new file)

### Django Specific Commands
- Create virtual environment: ```python3 -m venv <virtual environment name>```

- Activate virtual environment: ```source <virtual environment name>/bin/activate```

- Deactivate virtual environment: ```deactivate```

- Install django: ```pip install django```

- Start project: ```django-admin start project <project_name>```

- Starting django project in existing directory: ```django-admin start project <project_name> .```

- Delete project: ```rm -r <project_name>```

- Add apps to project: ```python manage.py startup <app_name>```

- Run Server: ```python manage.py runserver```
