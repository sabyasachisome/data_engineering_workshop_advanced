# data_engineering_workshop_advanced
🔹 Phase 1: Ingestion
SQS (ingestion_queue)
 → Lambda
   → Batch
     → ECS container
       → chamber
         → ingestion script
           → writes S3
           → prepares partition list
           → sends SQS (partition queue)

🔹 Phase 2: Partition Adder
SQS (partition_queue)
 → Lambda
   → Batch
     → ECS container
       → chamber
         → glue add-partition