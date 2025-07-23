# Topic 1: Airflow Use Cases 
- Given a specific scenario, identify if Airflow is an applicable solution. 
# Topic 2: Airflow Concepts 
- Identify which folder the Airflow Scheduler parses when searching for new DAG files: /dags
- Identify what an Airflow provider is: Integration with third party projects
- Identify what a DAG run is: 
	- Airflow runs DAGs in six different steps:
		- The DAG File Processor constantly scans the DAGs directory for new files. The default time is every 5 minutes.
		- After the DAG File Processor detects a new DAG, the DAG is processed and serialized into the metadata database.
		- The scheduler checks for DAGs that are ready to run in the metadata database. The default time is every 5 seconds for new files and 30 seconds for modification. 
		- Once a DAG is ready to run, its tasks are put into the executor's queue.
		- Once a worker is available, it will retrieve a task to execute from the queue.
		- The worker will then execute the task.
- Identify the role of a worker in Airflow: Airflow component that is in charge of executing the logic of a DAG's tasks
- Identify which programming language Airflow primarily uses.: python
- Identify the purpose of an XCom: Store values 
- Identify the purpose of a DAG 
- Identify the purpose of the `default_args` DAG parameter 
- Identify the default time zone of an Airflow instance: UTC
- Identify the role of an executor in Airflow:  To determine how and where tasks are executed
- Identify the role of the scheduler: To both trigger scheduled workflows and submit tasks to the executor to run
- Identify the core architectural components of Airflow
![[Pasted image 20250722082830.png]]
- Identify the typical journey of a task ![[Pasted image 20250722083217.png]]
- Identify what happens when two DAGs share the same `dag_id`
- Identify optional and non-optional DAG parameters
- Identify what each of the task lifecycle stages does
- Identify valid ways to define a DAG in Airflow. 
	- A DAG has four core parts:
		- The import statements, where the specific operators or classes that are needed for the DAG are defined.
		- The DAG definition, where the DAG object is called and where specific properties, such as its name or how often you want to run it, are defined.
		- The DAG body, where tasks are defined with the specific operators they will run.
		- The dependencies, where the order of execution of tasks is defined using the right bitshift operator (>>) and the left bitshift operator (<<).
# Topic 3: Dependencies
- Identify the purpose of task-level dependencies in Airflow: How tasks relate to each other and ultimately their execution order;
- Identify where DAG dependencies are set up in Airflow
- Compare and contrast DAG task dependency relationships for equivalency
- Match DAG task dependency graphs to their equivalent DAG dependency code. 
# Topic 4: Airflow CLI 
- Identify the purpose of specific Airflow CLI commands: 
	◦ `airflow tasks test` 
	◦ `airflow db init` : Initialize the metadata database
	◦ `airflow info : Show information about current Airflow and environment
	◦ `airflow tasks test` : test task from a dag
	◦ `airflow config list` View configuration
	◦ `airflow cheat sheet` : Display cheat sheet
	◦ `airflow variables` : Manage variables
	◦ `airflow users` : manager users
	◦ `airflow standalone` : Run an all-in-one copy of Airflow (only to dev)
	◦ `airflow version : Show the version
-  Identify the impact of using the Airflow `airflow tasks test` CLI command with a DAG that has an XCom.  : The xcom is not created and dependencies are not checked
# Topic 5: Airflow UI 
-  Identify the most helpful Airflow UI view to use for real-world scenarios. 
	◦ Grid view 
	- The grid view presents a history of task, and DAG Run states for a particular DAG, while the graph view visually represents task dependencies.
	◦ Graph view 
	◦ Gantt view 
	◦ DAGs view 
	 - list of all DAG Runs or task instances in the Airflow instance by going to DAGs view and then Runs or Task Instances.
	◦ Landing times view 
	◦ Tree view 
	◦ Calendar view 
- Identify the default time for DAGs to appear in the Airflow UI: 5 minutes
- Identify the result of deleting a DAG using the Airflow UI
- Identify the purpose of core Airflow UI components (e.g., The Last Run Column): 
- Given a specific Airflow UI, identify solutions to common issues.
# Topic 6: DAG Scheduling 
- Identify the purpose of each DAG scheduling parameter:  
	◦ `catchup` 
	◦ `start_date` 
	◦ `end_date` 
	◦ `schedule_interval` 
- Identify which tools/commands make it possible to backfill DAGs when the parameter `catchup` is set to `false`
- Identify the default value for the parameter `start_date`: None, it runs only manually
- Identify the valid values a DAG can accept for its `schedule_interval` parameter: ![[Pasted image 20250722082307.png]]
- Given a specific DAG scheduling goal (e.g., Schedule a DAG every day at 2 PM), identify the correct DAG scheduling parameter values to accomplish the goal
- Given specific DAG scheduling parameter values, identify if a specific scheduling goal will be accomplished: Can run with @operator, CRON expression or pendulum date objects (duration: interval of time)
- If CREATE_CRON_DATA_INTERVALS= False(default), the dag data_interval_start, data_interval_end and logical_date are the same, it runs with the date. If it's True, the DAG wait the interval from the data_interval_start, after that it runs. 

# Topic 7: DAG Runs 
 - Given a specific DAG scheduling scenario or DAG code, identify the number of DAG runs that will occur. 
 - By standard, 16 runs dags at the same time
 - DAG can have 4 states: queued, running, success, failed
# Topic 8: Debugging 
- Given a specific Airflow issue or completed DAG code, identify the cause of it. 
	- Check dags in metadata store: astro dev run dags list
	- astro dev logs -s: list logs of the scheduler
	- airflow dags list-import-errors
	- max_active_runs_per_dag: 16
	- max_active_tasks_per_dag: 16
	- parallelism: 32
# Topic 9: XComs 
- Identify the purpose of each XCom method: 
	◦ `xcom push` 
	◦ `xcom pull` 
- Identify the limitations of using XComs: Data must be serializable 
	- SQLite: 2GB
	- Postgres: 1GB
	- MySQL: 64MB
# Topic 10: Operators 
 - Identify what a Transfer Operator does: Transfer files
 - Identify what a Sensor Operator does 
 - Identify the purpose of the Airflow PythonOperator 
# Topic 11: Best Practices 
 - Given specific DAG code, identify ways to improve the code using Airflow best practices. 
# Topic 12: Connections 
- Identify the different ways to create an Airflow connection: 
	- Airflow UI > Admin> Connection > Add Connection 
	- DAG with a specific provider (conn_id can be a .env variable or from ui)
- Identify the correct way to create an Airflow connection in a `.env` file: AIRFLOW_CONN_{name of the connection}
- Given a specific Airflow connection string, identify the connection ID 
- Connections must have a unique connection ID, set of parameters (login, password, hostname..) and encrypted
- Must install the provider package 
# Topic 13: Tasks 
- Given DAG code, identify the number of tasks that will run when the DAG is scheduled. 
# Topic 14: Sensors 
- Identify the default timeout value of a sensor: 7 days
- Identify the mode to use in a DAG when the DAGs poke_interval parameter value is set to specific durations : default poke_interval: 60s
- Given the code for a sensor in a DAG, identify if the sensor is properly configured to accomplish a specific goal. 
- reschedule: the worker will be released from work. the status of the taks is up_for_reschedule 
- exponential_backoff: exponentially increase the time of the poke 
# Topic 15: Variables 
- Identify the purpose of an Airflow variable: avoid hard code in dags. Stored in the metabase
- Identify the types of data that can be stored in a variable. key: value pair or short Json 
- Identify the correct way to define a variable with a specific value in Airflow: if has some key words, the value is hidden  
- In .env: AIRFLOW_VAR_{variable name}
- Identify how to fetch the value of an Airflow variable in specific formats (e.g., JSON): Variable.get("name_var", deserialize_json=True)
- Given a specific variable name, Identify if a variable will be visible in the Airflow UI

# Extra

```python
from airflow.sdk import dag, DAG, task
from pendulum import datetime

@dag(schedule="@daily",
	start_date=datetime(2025,1,1),
	description="This dags does...",
	tags = ["team_a","source_a"],
	max_consecutive_failed_dag_runs=3
)
def check_dag():
	
	@task.bash
	def create_file():
		return 'echo "Hi there!" > /tmp/dummy'

	@task.bash
	def check_file_exists():
		return 'test -f /tmp/dummy'

	@task
	def read_file():
		print(open('/tmp/dummy', 'rb').read())

create_file() >> check_file_exists() >> read_file()

check_dag()
```