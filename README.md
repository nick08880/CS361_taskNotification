# Task notification Microservice
    This microservice will create a due date notification for a tasks.
# Install Flask and install requests
    To get started make sure you have flask and requests installed. "pip install flask" and " pip install requests"
# Run Microservice 
Using a terminal, type the following commands
**python notification_microservice.py**  
and for the second program 
**python test_program.py**
# How to programmatically REQUEST data from the microservice
To add a task, you send a POST request to the /add_task endpoint with a JSON payload containing the task name and due date. 
Code:

```
def add_task(task_name, due_date):
    url = 'http://127.0.0.1:5000/add_task'
    data = {
        'task_name': task_name,
        'due_date': due_date
    }
    response = requests.post(url, json=data)
    if response.status_code == 200:
        print(response.json()['message'])
    else:
        print(f"Error: {response.json()['error']}")
```
```
 Example CAll: # This will send a task named "example_task" and due date "2024-08-24". The response from the microservice will be printed out.
curl -X POST http://127.0.0.1:5000/add_task -H "Content-Type: application/json" -d '{"task_name": "example_task", "due_date": "2024-08-24"}'

```

#  How to programmatically RECEIVE data
Send a GET request to the /notify endpoint with the task name as a query parameter.
```
import requests

def notify(task_name):
    response = requests.get(f'http://127.0.0.1:5000/notify?task_name={task_name}')
    if response.status_code == 200:
        print(response.json()['message'])
    else:
        print(f"Error: {response.json()['error']}")
```
Example Call:
notify('example_task')


<img width="404" alt="Screenshot 2024-08-06 at 5 50 50 PM" src="https://github.com/user-attachments/assets/bd656395-9d64-462d-aa2d-03fad630e829">



# Mitigation / Communication Contract
For which teammate did you implement “Microservice A”?
    **Reggie**
What is the current status of the microservice?
    **Done**
  
How is your teammate going to access your microservice? Should they get your code from GitHub? Should they run your code locally? Is your microservice hosted somewhere? Etc.
    **Can be accessed on github and run locally**
If your teammate cannot access/call YOUR microservice, what should they do? Can you be available to help them? What’s your availability?
    **Contac me I will respond wihtin 24 hours**
If your teammate cannot access/call your microservice, by when do they need to tell you?
    **Friday or Saturday**
Is there anything else your teammate needs to know? Anything you’re worried about? Any assumptions you’re making? Any other mitigations / backup plans you want to mention or want to discuss with your teammate?
    **N/A** 
