# MYSQL Database is Slow ??

- Check OS to make sure that the system is running fine.
- Check CPU, memory, SWAP space and disk IO.
- Check running queries
    - show full processlist;
    - | Id | User | Host | db | Command | Time | State | Info | Progress |
    
- Investigate queries for lack of primary keys
    -  id | select_type | table | type | possible_keys | key | key_len | ref | rows | Extra

- Enable slow queries log file
    - /etc/mysql/mysql.cnf 
        - log_slow_queries = /var/log/mysql/mysql-slow.log
        - long_query_time = 2  (logs any queries that takes longer than 2 seconds)
        - log_queries_not_using_indexes (log queries that do not have index)

- Query cache 
    - show variables like 'have_query_cache'
    - show status like 'Qcache%' 

