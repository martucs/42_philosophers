# 42_philosophers
A project about threads and mutexes

Input in ms:

    ./philo philo_num  philo_num  time_to_die  time_to_eat  time_to_sleep  [meals_to_die]

If you want all philos to LIVE:


time_to_die has to be >= time_to_eat + time_to_sleep

time_to_die has to be 3 times bigger than time_to_eat when philo_num is an odd number!

time_to_sleep has to be < than time_to_die / 2

About my code
 -------------------------------------------------------------------------------


- I have 1 general mutex for all philos to use when they want to print in stdout (print_mutex)

- It works correctly with 200 philos

- I have a linked list for the philosophers and an array of mutexes for the forks

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

Things that could be improved:

- Each philo has their own 'check_mutex' to protect three individual variables -> it would probably be better to have a mutex x variable.

  This would make the program run faster and allow the philos not to rely on the same mutex for everything. On the other hand, it would be another mutex to create, initialize and destroy, so it could take up more memory space.
- Cleaner code for the actions of the life cyle
- It would be better to have one special case for when philo_num = 1 instead of a while inside the life cycle cause it is a check that happens each time any philospher eats
