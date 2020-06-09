## Storage Accounts, 

- Creating and configuring a storage account, 
- Azure Storage Explorer, 
- Network access to the storage account, 
- Generating and managing SAS, 
- Azure storage replication.

Azure 提供了很多类型的storage account，可以被用来存各种不同类型的数据。Files, Documents, Datasets, Blobs, VHDs(Virtual Hard Disks).

三种不同的storage account type: 可以被用于 Blob, Table, File, Queue

- GPv1 (General-purpose v1)是最老的一种storage account，它提供了page blobs, block blobs, files, queues, and tables.
- Blob storage。这种不支持page blobs.并增加了access tiers（hot, cool, archive）
- GPv2 是最新的一种storage account。支持最多的功能，费用也比较便宜。是微软最推荐使用的storage account。

关于费用  https://azure.microsoft.com/en-us/pricing/details/storage/

### Storage Replication Types

- Locally Redundant Storage (LRS)
- Zone Redundant Storage (ZRS)
- Geo-Redundant Storage (GRS)
- Geo-Zone-Redundant Storage (GZRS)
- Read-Access Geo-Redundant Storage (RA-GRS)

LRS 是最便宜的，它会在同一个数据中心复制三份。当你对storage account进行一次写操作时，他会同步写三份备份，而只有三份数据都写入完成，这次写操作才算是成功了。

ZRS 也是将数据复制三份，并会将他们放在两到三个不同的数据中心。数据的写入也是同步的。同时在每个data center内部，数据还是会被复制两到三份。

GRS 则是在同一个region复制数据，并且会异步地复制三份到其他的region。
