# s3lambdachichao

Given a Lambda function that is triggered upon the creation of files in an S3 bucket, answer the following:
1. What is the purpose of the execution role on the Lambda function?
<span style="color: red;">Ans : Grants the Lambda function permissions to access or interact with other AWS services (for example, allowing s3:PutObject on a bucket).</span>
   
2. What is the purpose of the resource-based policy on the Lambda function?
Ans : Controls who or what can invoke (call) the Lambda function (e.g., allowing S3 to trigger the function upon object creation).
 
3. If the function is needed to upload a file into an S3 bucket, describe (i.e no need for the actual policies)
   - What is the needed update on the execution role?
   Ans : It must add "s3:PutObject" permissions (and possibly "s3:PutObjectAcl" if necessary) to the execution role policy so the function can upload objects to S3.

   - What is the new resource-based policy that needs to be added (if any)?
   Ans : Typically not required just for uploading to S3. The resource-based policy on Lambda only concerns inbound calls (e.g., letting S3 invoke the function), not outbound calls.
