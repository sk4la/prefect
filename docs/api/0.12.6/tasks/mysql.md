---
sidebarDepth: 2
editLink: false
---
# MySQL Tasks
---
This module contains a collection of tasks for interacting with MySQL databases via
the pymysql library.
 ## MySQLExecute
 <div class='class-sig' id='prefect-contrib-tasks-mysql-mysql-mysqlexecute'><p class="prefect-sig">class </p><p class="prefect-class">prefect.contrib.tasks.mysql.mysql.MySQLExecute</p>(db_name, user, password, host, port=3307, query=None, commit=False, charset="utf8mb4", **kwargs)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/contrib/tasks/mysql/mysql.py#L9">[source]</a></span></div>

Task for executing a query against a MySQL database.

**Args**:     <ul class="args"><li class="args">`db_name (str)`: name of MySQL database     </li><li class="args">`user (str)`: user name used to authenticate     </li><li class="args">`password (str)`: password used to authenticate     </li><li class="args">`host (str)`: database host address     </li><li class="args">`port (int, optional)`: port used to connect to MySQL database, defaults to 3307         if not provided     </li><li class="args">`query (str, optional)`: query to execute against database     </li><li class="args">`commit (bool, optional)`: set to True to commit transaction, defaults to false     </li><li class="args">`charset (str, optional)`: charset you want to use (defaults to utf8mb4)     </li><li class="args">`**kwargs (Any, optional)`: additional keyword arguments to pass to the         Task constructor</li></ul>

|methods: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:----|
 | <div class='method-sig' id='prefect-contrib-tasks-mysql-mysql-mysqlexecute-run'><p class="prefect-class">prefect.contrib.tasks.mysql.mysql.MySQLExecute.run</p>(query=None, commit=False, charset="utf8mb4")<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/contrib/tasks/mysql/mysql.py#L49">[source]</a></span></div>
<p class="methods">Task run method. Executes a query against MySQL database.<br><br>**Args**:     <ul class="args"><li class="args">`query (str, optional)`: query to execute against database     </li><li class="args">`commit (bool, optional)`: set to True to commit transaction, defaults to False     </li><li class="args">`charset (str, optional)`: charset of the query, defaults to "utf8mb4"</li></ul>**Returns**:     <ul class="args"><li class="args">`executed (int)`: number of affected rows</li></ul>**Raises**:     <ul class="args"><li class="args">pymysql.MySQLError</li></ul></p>|

---
<br>

 ## MySQLFetch
 <div class='class-sig' id='prefect-contrib-tasks-mysql-mysql-mysqlfetch'><p class="prefect-sig">class </p><p class="prefect-class">prefect.contrib.tasks.mysql.mysql.MySQLFetch</p>(db_name, user, password, host, port=3307, fetch="one", fetch_count=10, query=None, commit=False, charset="utf8mb4", **kwargs)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/contrib/tasks/mysql/mysql.py#L95">[source]</a></span></div>

Task for fetching results of query from MySQL database.

**Args**:     <ul class="args"><li class="args">`db_name (str)`: name of MySQL database     </li><li class="args">`user (str)`: user name used to authenticate     </li><li class="args">`password (str)`: password used to authenticate     </li><li class="args">`host (str)`: database host address     </li><li class="args">`port (int, optional)`: port used to connect to MySQL database, defaults to 3307 if not         provided     </li><li class="args">`fetch (str, optional)`: one of "one" "many" or "all", used to determine how many         results to fetch from executed query     </li><li class="args">`fetch_count (int, optional)`: if fetch = 'many', determines the number of results to         fetch, defaults to 10     </li><li class="args">`query (str, optional)`: query to execute against database     </li><li class="args">`commit (bool, optional)`: set to True to commit transaction, defaults to false     </li><li class="args">`charset (str, optional)`: charset of the query, defaults to "utf8mb4"     </li><li class="args">`**kwargs (Any, optional)`: additional keyword arguments to pass to the         Task constructor</li></ul>

|methods: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:----|
 | <div class='method-sig' id='prefect-contrib-tasks-mysql-mysql-mysqlfetch-run'><p class="prefect-class">prefect.contrib.tasks.mysql.mysql.MySQLFetch.run</p>(fetch="one", fetch_count=10, query=None, commit=False, charset="utf8mb4")<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/contrib/tasks/mysql/mysql.py#L143">[source]</a></span></div>
<p class="methods">Task run method. Executes a query against MySQL database and fetches results.<br><br>**Args**:     <ul class="args"><li class="args">`fetch (str, optional)`: one of "one" "many" or "all", used to determine how many         results to fetch from executed query     </li><li class="args">`fetch_count (int, optional)`: if fetch = 'many', determines the number of results         to fetch, defaults to 10     </li><li class="args">`query (str, optional)`: query to execute against database     </li><li class="args">`commit (bool, optional)`: set to True to commit transaction, defaults to false     </li><li class="args">`charset (str, optional)`: charset of the query, defaults to "utf8mb4"</li></ul>**Returns**:     <ul class="args"><li class="args">`results (tuple or list of tuples)`: records from provided query</li></ul>**Raises**:     <ul class="args"><li class="args">pymysql.MySQLError</li></ul></p>|

---
<br>


<p class="auto-gen">This documentation was auto-generated from commit <a href='https://github.com/PrefectHQ/prefect/commit/n/a'>n/a</a> </br>on August 6, 2020 at 13:56 UTC</p>