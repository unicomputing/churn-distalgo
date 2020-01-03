# Churn
This is DistAlgo implementation and testing of Churn algorithm defined in the paper 
"Emulating a Shared Register in a System That Never Stops Changing", IEEE TRANSACTIONS
ON PARALLEL AND DISTRIBUTED SYSTEMS, VOL. 30, NO. 3, MARCH 2019, pp. 544-559, Hagit Attiya
, Hyun Chul Chung, Faith Ellen, Saptaparni Kumar, and Jennifer L. Welch

# Requirements
## Python
DistAlgo requires Python version 3.5 or higher.
## DistAlgo
DistAlgo is a very high-level language for programming distributed algorithms.
Installation step: https://github.com/DistAlgo/distalgo/blob/c58d13c61fc115cad3c1eac05fbb3645095e7671/README.md
The repo is tested on pyDistAlgo version 1.0.13.

# Running the program
The paper defines a range of permissible values of (ɑ, 𝛃, 𝞬, Δ, D). The simulation can 
assume any value of the parameter within this range. The step size, begin and
end is define for each of these parameters.

For performance testing, the test needs to be repeated for multiple range of
these values. In the single run of the program, it iterates through all the values
of anyone of the chosen parameter.

Apart from the above parameters there are other system parameters defined for the simulation:
- Node_count - number of nodes at the start of the simulation.
- sleep_time_node - number of seconds the node is sent to sleep.
- Max_delay - maximum amount of time taken for transmitting message (D).
- num_of_rounds - number of times the all the tests need to be repeated.
- num_read_writes - number of times read/write test is performed.
- churn_count - number of times leave/join test is performed.
- Retention_limit - number

## Sample Run:
```
$ python -d -m da  --message-buffer-size 1000000 churn.da 
churn.da compiled with 0 errors and 0 warnings.
Written compiled file churn.py.
certify.da compiled with 0 errors and 0 warnings.
Written compiled file certify.py.
[249] da.api<MainProcess>:INFO: <Node_:e2801> initialized at 127.0.0.1:(UdpTransport=37319, TcpTransport=24572).
[249] da.api<MainProcess>:INFO: Starting program <module 'churn' from '/Users/divyam/Dev/async/project/churn-distalgo/churn.py'>...
[249] da.api<MainProcess>:INFO: Running iteration 1 ...
[250] da.api<MainProcess>:INFO: Waiting for remaining child processes to terminate...(Press "Ctrl-C" to force kill)
[251] churn.Node_<Node_:e2801>:OUTPUT: RETEN_COUNT is 10
[251] churn.Node_<Node_:e2801>:OUTPUT: *******************NUM_NODES******************* 30.0
[865] churn.Scheduler<Scheduler:ad803>:OUTPUT: nodes present initially are {<Node:ad81f>, <Node:ad81d>, <Node:ad81c>, <Node:ad815>, <Node:ad811>, <Node:ad80c>, <Node:ad818>, <Node:ad80a>, <Node:ad812>, <Node:ad80b>, <Node:ad816>, <Node:ad80d>, <Node:ad80f>, <Node:ad810>, <Node:ad814>, <Node:ad804>, <Node:ad807>, <Node:ad808>, <Node:ad81a>, <Node:ad80e>, <Node:ad819>, <Node:ad821>, <Node:ad813>, <Node:ad820>, <Node:ad817>, <Node:ad806>, <Node:ad805>, <Node:ad81e>, <Node:ad809>, <Node:ad81b>}
[867] churn.Scheduler<Scheduler:ad803>:OUTPUT: ROUND NUMBER: 0
[867] churn.Scheduler<Scheduler:ad803>:OUTPUT: Enter-Leave count: 0
[868] churn.Scheduler<Scheduler:ad803>:OUTPUT: randomly chosen node is <Node:ad813>
[868] certify.Certifier<Certifier:ad802>:OUTPUT: {<Node:ad81f>, <Node:ad81d>, <Node:ad81c>, <Node:ad815>, <Node:ad811>, <Node:ad80c>, <Node:ad818>, <Node:ad80a>, <Node:ad812>, <Node:ad80b>, <Node:ad816>, <Node:ad80d>, <Node:ad80f>, <Node:ad810>, <Node:ad814>, <Node:ad804>, <Node:ad807>, <Node:ad81a>, <Node:ad808>, <Node:ad80e>, <Node:ad819>, <Node:ad821>, <Node:ad813>, <Node:ad820>, <Node:ad817>, <Node:ad806>, <Node:ad805>, <Node:ad81e>, <Node:ad809>, <Node:ad81b>}
[870] churn.Scheduler<Scheduler:ad803>:OUTPUT: making <Node:ad813> node leave
[870] churn.Node<Node:ad813>:OUTPUT: received leave signal
[1369] churn.Node<Node:ad813>:OUTPUT: leave_bound set to 22.2 based on Present size of 30
[2236] churn.Node<Node:ad813>:OUTPUT: size of Changes: 61 and state_num:1
[2440] churn.Node<Node:ad813>:OUTPUT: exiting...
[2450] churn.Scheduler<Scheduler:ad803>:OUTPUT: Leave operation completed for  <Node:ad813>
[4868] churn.Scheduler<Scheduler:ad803>:OUTPUT: Enter-Leave count: 1
[5462] churn.Node<Node:ad822>:OUTPUT: entered, bcasted enter msgs
[5489] churn.Node<Node:ad822>:OUTPUT: join_bound set to 22.2 based on Present size of 30
[6266] churn.Node<Node:ad822>:OUTPUT: joined
[6266] churn.Node<Node:ad822>:OUTPUT: size of Changes: 60
[6267] churn.Node<Node:ad822>:OUTPUT: size of Changes: 60 and state_num:2
[7260] churn.Node<Node:ad822>:OUTPUT: sent joined to scheduler
[7260] churn.Scheduler<Scheduler:ad803>:OUTPUT: join operation completed for  <Node:ad822>
[8871] churn.Scheduler<Scheduler:ad803>:OUTPUT: Enter-Leave count: 2
[8965] churn.Node<Node:ad823>:OUTPUT: entered, bcasted enter msgs
[8992] churn.Node<Node:ad823>:OUTPUT: join_bound set to 22.94 based on Present size of 31
[9611] churn.Node<Node:ad823>:OUTPUT: joined
[9612] churn.Node<Node:ad823>:OUTPUT: size of Changes: 62
[9612] churn.Node<Node:ad823>:OUTPUT: size of Changes: 62 and state_num:3
[10075] churn.Node<Node:ad823>:OUTPUT: sent joined to scheduler
[10075] churn.Scheduler<Scheduler:ad803>:OUTPUT: join operation completed for  <Node:ad823>
[12878] churn.Scheduler<Scheduler:ad803>:OUTPUT: Enter-Leave count: 3
[12878] churn.Scheduler<Scheduler:ad803>:OUTPUT: randomly chosen node is <Node:ad808>
[12885] churn.Scheduler<Scheduler:ad803>:OUTPUT: making <Node:ad808> node leave
[12886] churn.Node<Node:ad808>:OUTPUT: received leave signal
[13567] churn.Node<Node:ad808>:OUTPUT: leave_bound set to 22.94 based on Present size of 31
[14277] churn.Node<Node:ad808>:OUTPUT: size of Changes: 64 and state_num:4
[14760] churn.Node<Node:ad808>:OUTPUT: exiting...
[14768] churn.Scheduler<Scheduler:ad803>:OUTPUT: Leave operation completed for  <Node:ad808>
[16880] churn.Scheduler<Scheduler:ad803>:OUTPUT: Enter-Leave count: 4
[17866] churn.Node<Node:ad824>:OUTPUT: entered, bcasted enter msgs
[17895] churn.Node<Node:ad824>:OUTPUT: join_bound set to 22.94 based on Present size of 31
[18346] churn.Node<Node:ad824>:OUTPUT: joined
[18346] churn.Node<Node:ad824>:OUTPUT: size of Changes: 63
[18347] churn.Node<Node:ad824>:OUTPUT: size of Changes: 63 and state_num:5
[18839] churn.Node<Node:ad824>:OUTPUT: sent joined to scheduler
[18840] churn.Scheduler<Scheduler:ad803>:OUTPUT: join operation completed for  <Node:ad824>
[20883] churn.Scheduler<Scheduler:ad803>:OUTPUT: Enter-Leave count: 5
[20883] churn.Scheduler<Scheduler:ad803>:OUTPUT: randomly chosen node is <Node:ad81c>
[20886] churn.Scheduler<Scheduler:ad803>:OUTPUT: making <Node:ad81c> node leave
[20886] churn.Node<Node:ad81c>:OUTPUT: received leave signal
[21176] churn.Node<Node:ad81c>:OUTPUT: leave_bound set to 22.94 based on Present size of 31
[21818] churn.Node<Node:ad81c>:OUTPUT: size of Changes: 65 and state_num:6
[22681] churn.Node<Node:ad81c>:OUTPUT: exiting...
[22690] churn.Scheduler<Scheduler:ad803>:OUTPUT: Leave operation completed for  <Node:ad81c>
[24885] churn.Scheduler<Scheduler:ad803>:OUTPUT: Enter-Leave count: 6
[25549] churn.Node<Node:ad825>:OUTPUT: entered, bcasted enter msgs
[25593] churn.Node<Node:ad825>:OUTPUT: join_bound set to 22.94 based on Present size of 31
[26393] churn.Node<Node:ad825>:OUTPUT: joined
[26393] churn.Node<Node:ad825>:OUTPUT: size of Changes: 64
[26393] churn.Node<Node:ad825>:OUTPUT: size of Changes: 64 and state_num:7
[27155] churn.Node<Node:ad825>:OUTPUT: sent joined to scheduler
[27155] churn.Scheduler<Scheduler:ad803>:OUTPUT: join operation completed for  <Node:ad825>
[28887] churn.Scheduler<Scheduler:ad803>:OUTPUT: Enter-Leave count: 7
[28888] churn.Scheduler<Scheduler:ad803>:OUTPUT: randomly chosen node is <Node:ad805>
[28890] churn.Scheduler<Scheduler:ad803>:OUTPUT: making <Node:ad805> node leave
[28891] churn.Node<Node:ad805>:OUTPUT: received leave signal
[29366] churn.Node<Node:ad805>:OUTPUT: leave_bound set to 22.94 based on Present size of 31
[30086] churn.Node<Node:ad805>:OUTPUT: size of Changes: 66 and state_num:8
[30969] churn.Node<Node:ad805>:OUTPUT: exiting...
[30978] churn.Scheduler<Scheduler:ad803>:OUTPUT: Leave operation completed for  <Node:ad805>
[32891] churn.Scheduler<Scheduler:ad803>:OUTPUT: Enter-Leave count: 8
[32963] churn.Node<Node:ad826>:OUTPUT: entered, bcasted enter msgs
[33041] churn.Node<Node:ad826>:OUTPUT: join_bound set to 22.94 based on Present size of 31
[33778] churn.Node<Node:ad826>:OUTPUT: joined
[33778] churn.Node<Node:ad826>:OUTPUT: size of Changes: 65
[33778] churn.Node<Node:ad826>:OUTPUT: size of Changes: 65 and state_num:9
[34261] churn.Node<Node:ad826>:OUTPUT: sent joined to scheduler
[34261] churn.Scheduler<Scheduler:ad803>:OUTPUT: join operation completed for  <Node:ad826>
[36894] churn.Scheduler<Scheduler:ad803>:OUTPUT: Enter-Leave count: 9
[37198] churn.Node<Node:ad827>:OUTPUT: entered, bcasted enter msgs
[37263] churn.Node<Node:ad827>:OUTPUT: join_bound set to 23.68 based on Present size of 32
[37902] churn.Node<Node:ad827>:OUTPUT: joined
[37902] churn.Node<Node:ad827>:OUTPUT: size of Changes: 67
[37903] churn.Node<Node:ad827>:OUTPUT: size of Changes: 67 and state_num:10
[38876] churn.Node<Node:ad827>:OUTPUT: sent joined to scheduler
[38876] churn.Scheduler<Scheduler:ad803>:OUTPUT: join operation completed for  <Node:ad827>
[40897] churn.Scheduler<Scheduler:ad803>:OUTPUT: Randomly chosen node to crash  <Node:ad814>
[40897] churn.Scheduler<Scheduler:ad803>:OUTPUT: Sending sleep to  <Node:ad825>
[40898] churn.Scheduler<Scheduler:ad803>:OUTPUT: Exited the loop
[40899] churn.Node<Node:ad825>:OUTPUT: sleeping for 1 second
[45873] churn.Node_<Node_:e2801>:OUTPUT: sent done to scheduler at 1577687945.343903
[45874] churn.Scheduler<Scheduler:ad803>:OUTPUT: done received by scheduler
[45874] churn.Scheduler<Scheduler:ad803>:OUTPUT: total nodes in the system {<Node:ad81f>, <Node:ad81d>, <Node:ad824>, <Node:ad815>, <Node:ad811>, <Node:ad80c>, <Node:ad818>, <Node:ad80a>, <Node:ad812>, <Node:ad825>, <Node:ad80b>, <Node:ad816>, <Node:ad80d>, <Node:ad80f>, <Node:ad810>, <Node:ad814>, <Node:ad827>, <Node:ad804>, <Node:ad807>, <Node:ad81a>, <Node:ad80e>, <Node:ad826>, <Node:ad819>, <Node:ad821>, <Node:ad820>, <Node:ad823>, <Node:ad817>, <Node:ad806>, <Node:ad81e>, <Node:ad822>, <Node:ad809>, <Node:ad81b>}
[45875] churn.Node_<Node_:e2801>:OUTPUT: sent check correctness to Certifier
[45876] certify.Certifier<Certifier:ad802>:OUTPUT: EnterLeave order is:  [[1577687900.340003, 'leave', 30], [1577687904.341409, 'enter', 29], [1577687908.343765, 'enter', 30], [1577687912.355396, 'leave', 31], [1577687916.3533618, 'enter', 30], [1577687920.35618, 'leave', 31], [1577687924.358529, 'enter', 30], [1577687928.3606322, 'leave', 31], [1577687932.3634071, 'enter', 30], [1577687936.366796, 'enter', 31]]
[45876] certify.Certifier<Certifier:ad802>:OUTPUT: Testing join times of nodes
[45877] certify.Certifier<Certifier:ad802>:OUTPUT: Join time is within permissible range for all nodes
[45877] certify.Certifier<Certifier:ad802>:OUTPUT: Outputting crashed nodes {<Node:ad814>}
+--------------+-------------+----------+
| Process ID   |   Join Time | Reason   |
+==============+=============+==========+
| <Node:ad822> |    1.79802  | -        |
+--------------+-------------+----------+
| <Node:ad823> |    1.10961  | -        |
+--------------+-------------+----------+
| <Node:ad824> |    0.973255 | -        |
+--------------+-------------+----------+
| <Node:ad825> |    1.60688  | -        |
+--------------+-------------+----------+
| <Node:ad826> |    1.2988   | -        |
+--------------+-------------+----------+
| <Node:ad827> |    1.6777   | -        |
+--------------+-------------+----------+
+--------------+--------------+----------+
| Process ID   | Write Time   | Reason   |
+==============+==============+==========+
+--------------+--------------+----------+
+--------------+-------------+----------+
| Process ID   | Read Time   | Reason   |
+==============+=============+==========+
+--------------+-------------+----------+
[45882] churn.Scheduler<Scheduler:ad803>:OUTPUT: scheduler terminating
[55883] certify.Certifier<Certifier:ad802>:OUTPUT: TO / Writing to file
[55883] certify.Certifier<Certifier:ad802>:OUTPUT: Writing to file
[55884] certify.Certifier<Certifier:ad802>:OUTPUT: Read write order is:  []
[55885] certify.Certifier<Certifier:ad802>:OUTPUT: ### Correctness tests passed
[55888] da.api<MainProcess>:INFO: Main process terminated.
```
