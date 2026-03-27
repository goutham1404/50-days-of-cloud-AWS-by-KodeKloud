# Day 4: Enable Versioning for S3 Bucket 

Data protection and recovery are fundamental aspects of data management. It's essential to have systems in place to ensure that data can be recovered in case of accidental deletion or corruption. The DevOps team has received a requirement for implementing such measures for one of the S3 buckets they are managing. 

The s3 bucket name is `nautilus-s3-17892`, enable versioning for this bucket.

-----------------------------------------------------------------------------------

Method 1: From AWS CLI
----------------------
```sh
$ aws s3api put-bucket-versioning --bucket nautilus-s3-17892 --versioning-configuration Status=Enabled   # enables versioning on the S3 bucket

$ aws s3api get-bucket-versioning --bucket nautilus-s3-17892    # verify if versioning is enabled (should show "Status": "Enabled")
```

----------------------------------------------------------------------------------------------------------

Method 1: From AWS CLI
----------------------
```sh

```

Method 2: From via AWS Management Console
-----------------------------------------


**To allocate an Elastic IP address**

1. Sign in to the AWS Management Console and open the Amazon S3 console at [https://console.aws.amazon.com/s3](https://console.aws.amazon.com/s3)

2. In the left navigation pane, choose `General purpose buckets`.
   
   <img width="255" height="201" alt="Screenshot 2026-03-27 220008" src="https://github.com/user-attachments/assets/3f00877e-ddc7-4f29-823e-4f13da89c153" />

3. In the buckets list, choose the name of the bucket that you want to enable versioning for.

   <img width="1018" height="183" alt="Screenshot 2026-03-27 220058" src="https://github.com/user-attachments/assets/a9d25dce-fa98-45be-bc98-4e5e8db78763" />

4. Choose `Properties`.

   <img width="1064" height="251" alt="Screenshot 2026-03-27 220236" src="https://github.com/user-attachments/assets/b753fa24-7504-438f-b09a-a4533c370ea0" />

5. Under `Bucket Versioning`, Choose `Edit`.

   <img width="1064" height="338" alt="Screenshot 2026-03-27 220304" src="https://github.com/user-attachments/assets/5979485e-7b88-40b3-a22e-1065a6a930cc" />

6. Under `Bucket Versioning`, Choose `Enable`.

   <img width="1064" height="622" alt="Screenshot 2026-03-27 220329" src="https://github.com/user-attachments/assets/2ad15ef0-340d-4774-87ec-65578ea8c0a7" />

7.  Choose `Save changes`.

8.  The `Show versions` option will appear in the `nautilus-s3-17892` bucket `object` page.

   <img width="1322" height="600" alt="Screenshot 2026-03-27 220410" src="https://github.com/user-attachments/assets/7ee20836-757d-4e32-bcb7-722bcb1390cc" />



