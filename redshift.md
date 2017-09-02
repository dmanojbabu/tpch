## TPCH DBgen is used to prepare the data sets

ubuntu@ip-172-xx-xx-xx:~/2.17.2/dbgen$ ./dbgen -h

TPC-H Population Generator (Version 2.17.2 build 0)
Copyright Transaction Processing Performance Council 1994 - 2010
USAGE:
dbgen [-{vf}][-T {pcsoPSOL}]
        [-s <scale>][-C <procs>][-S <step>]
        dbgen [-v] [-O m] [-s <scale>] [-U <updates>]

To generate files for cutomers, lineitem, orders, nation use the below options

-T c   -- generate cutomers ONLY
-T n   -- generate nation ONLY
-T o   -- generate orders/lineitem ONLY

To generate the SF=1 (1GB), validation database population, use:
        dbgen -vf -T C -s 1
        dbgen -vf -T L -s 1
        dbgen -vf -T n -s 1
        dbgen -vf -T o -s 1

## To load data into S3 using AWS CLI
  aws s3 cp ds_1gb/ s3://<<bucket_name>>/50gb --recursive 
  
  
