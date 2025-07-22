# Topic 1: Airflow Use Cases 
- Given a specific scenario, identify if Airflow is an applicable solution. 
# Topic 2: Airflow Concepts 
- Identify which folder the Airflow Scheduler parses when searching for new DAG files: /dags
- Identify what an Airflow provider is: Integration with third party projects
- Identify what a DAG run is
- Identify the role of a worker in Airflow
- Identify which programming language Airflow primarily uses.: python
- Identify the purpose of an XCom: Store values 
- Identify the purpose of a DAG 
- Identify the purpose of the `default_args` DAG parameter 
- Identify the default time zone of an Airflow instance: UTC
- Identify the role of an executor in Airflow: Execute the task passed by the scheduler
- Identify the role of the scheduler: To both trigger scheduled workflows and submit tasks to the executor to run
- Identify the core architectural components of Airflow
- Identify the typical journey of a task
- Identify what happens when two DAGs share the same `dag_id`
- Identify optional and non-optional DAG parameters
- Identify what each of the task lifecycle stages does
- Identify valid ways to define a DAG in Airflow. 
# Topic 3: Dependencies
- Identify the purpose of task-level dependencies in Airflow
- Identify where DAG dependencies are set up in Airflow
- Compare and contrast DAG task dependency relationships for equivalency
- Match DAG task dependency graphs to their equivalent DAG dependency code. 
# Topic 4: Airflow CLI 
- Identify the purpose of specific Airflow CLI commands: 
	◦ `airflow tasks test` 
	◦ `airflow db init` 
	◦ `airflow info 
	◦ `airflow tasks test` 
	◦ `airflow config list` 
	◦ `airflow cheat sheet` 
	◦ `airflow variables` 
	◦ `airflow users` 
	◦ `airflow standalone` 
	◦ `airflow version 
-  Identify the impact of using the Airflow `airflow tasks test` CLI command with a DAG that has an XCom.  
# Topic 5: Airflow UI 
-  Identify the most helpful Airflow UI view to use for real-world scenarios. 
	◦ Grid view 
	◦ Graph view 
	◦ Gantt view 
	◦ DAGs view 
	◦ Landing times view 
	◦ Tree view 
	◦ Calendar view 
- Identify the default time for DAGs to appear in the Airflow UI 
- Identify the result of deleting a DAG using the Airflow UI
- Identify the purpose of core Airflow UI components (e.g., The Last Run Column)
- Given a specific Airflow UI, identify solutions to common issues.
# Topic 6: DAG Scheduling 
- Identify the purpose of each DAG scheduling parameter:  
	◦ `catchup` 
	◦ `start_date` 
	◦ `end_date` 
	◦ `schedule_interval` 
- Identify which tools/commands make it possible to backfill DAGs when the parameter `catchup` is set to `false`
- Identify the default value for the parameter `start_date`
- Identify the valid values a DAG can accept for its `schedule_interval` parameter
- Given a specific DAG scheduling goal (e.g., Schedule a DAG every day at 2 PM), identify the correct DAG scheduling parameter values to accomplish the goal
- Given specific DAG scheduling parameter values, identify if a specific scheduling goal will be accomplished

# Topic 7: DAG Runs 
 - Given a specific DAG scheduling scenario or DAG code, identify the number of DAG runs that will occur. 
# Topic 8: Debugging 
- Given a specific Airflow issue or completed DAG code, identify the cause of it. 
# Topic 9: XComs 
- Identify the purpose of each XCom method: 
	◦ `xcom push` 
	◦ `xcom pull` 
- Identify the limitations of using XComs

# Topic 10: Operators 
 - Identify what a Transfer Operator does
 - Identify what a Sensor Operator does 
 - Identify the purpose of the Airflow PythonOperator 
# Topic 11: Best Practices 
 - Given specific DAG code, identify ways to improve the code using Airflow best practices. 
# Topic 12: Connections 
- Identify the different ways to create an Airflow connection 
- Identify the correct way to create an Airflow connection in a `.env` file 
- Given a specific Airflow connection string, identify the connection ID 
# Topic 13: Tasks 
- Given DAG code, identify the number of tasks that will run when the DAG is scheduled. 
# Topic 14: Sensors 
- Identify the default timeout value of a sensor
- Identify the mode to use in a DAG when the DAGs poke_interval parameter value is set to specific durations 
- Given the code for a sensor in a DAG, identify if the sensor is properly configured to accomplish a specific goal. 
# Topic 15: Variables 
- Identify the purpose of an Airflow variable
- Identify the types of data that can be stored in a variable 
- Identify the correct way to define a variable with a specific value in Airflow 
- Identify how to fetch the value of an Airflow variable in specific formats (e.g., JSON)
- Given a specific variable name, Identify if a variable will be visible in the Airflow UI