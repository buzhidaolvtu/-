# 问题
transaction -> redo log -> undo log -> buffer pool -> doublewrite buffer -> disk  
如果发生了crash,  
怎样判断哪些事物已经flush到disk中，哪些事物还在redo log中;  
怎样判断哪些事物需要undo，哪些需要redo;  
什么时机把事物的undo信息flush到undo log file中,与commit的时间点对比;  
如果事物已经记录到redo log中,这个事物的什么时候提交到buffer pool中,什么时候该事物具有可见性；
如果开启了doublewrite buffer,doublewrite buffer和disk的区别是什么，具体的作用是什么;  
什么是LSN;  
什么是Mini transaction;  
如果log buffer不足会发生什么;  

# 2018.01.30
https://www.percona.com/blog/2007/12/19/mvcc-transaction-ids-log-sequence-numbers-and-snapshots/

The LSN do not relate much to transactions – changes from different transactions are intermixed in the log files and many LSNs can correspond to changes from the same transaction.

