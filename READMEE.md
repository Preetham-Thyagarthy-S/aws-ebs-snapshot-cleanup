# AWS EBS Snapshot Cleanup (Cost Optimization)

## Project Overview

This project demonstrates a simple AWS cost optimization solution using **AWS Lambda**, **Python (Boto3)**, and **IAM**.

When an Amazon EC2 instance is deleted, its attached EBS volume can also be deleted. However, EBS snapshots remain in your AWS account until they are manually deleted, and they continue to incur storage charges.

This project automatically identifies and deletes unused EBS snapshots that are no longer associated with an active EC2 instance or an existing EBS volume.

---

## Problem Statement

When an EC2 instance is terminated:

* The EBS volume may be deleted.
* Existing snapshots are **not** deleted automatically.
* Unused snapshots continue to consume storage and may increase AWS costs.

This project automates the cleanup process to help reduce unnecessary storage costs.

---

## AWS Services Used

* Amazon EC2
* Amazon EBS
* AWS Lambda
* AWS IAM
* Amazon CloudWatch (Lambda Logs)
* Python (Boto3)

---

## Project Workflow

1. Launch an EC2 instance.
2. Create an EBS snapshot.
3. Delete the EC2 instance.
4. The associated EBS volume is removed.
5. Execute the AWS Lambda function.
6. The Lambda function checks all EBS snapshots.
7. If a snapshot belongs to a deleted or unused volume, it deletes the snapshot automatically.

---

## Python Script

The Python script uses the **Boto3** AWS SDK to:

* Retrieve all EBS snapshots.
* Check whether the associated EBS volume still exists.
* Verify whether the volume is attached to a running EC2 instance.
* Delete snapshots that are no longer required.

---

## Screenshots

### EC2 Instance

<img width="1366" height="634" alt="ec_2 instace" src="https://github.com/user-attachments/assets/58e86b69-31c9-4627-833e-174482efca7d" />


### EBS Volume

<img width="1359" height="652" alt="Volume_screenshot" src="https://github.com/user-attachments/assets/4f847f15-348b-4dc8-95f7-8ec4479368ce" />


### EBS Snapshot

<img width="1363" height="646" alt="snapshot-ss" src="https://github.com/user-attachments/assets/a3a0485e-8e62-48f1-a65f-5826c0b4d7a9" />


### Successful Lambda Execution

<img width="1351" height="609" alt="success-output" src="https://github.com/user-attachments/assets/9c7a8b09-1c43-4957-8e6e-c181dd42b8b9" />


### Snapshot Deleted

<img width="1360" height="641" alt="success-2" src="https://github.com/user-attachments/assets/6ec47ef7-19d2-46ac-b7dc-d841c1429990" />

---

## Learning Outcomes

* Learned how EBS snapshots work.
* Understood AWS cost optimization concepts.
* Created and configured an IAM role with the required permissions.
* Developed an AWS Lambda function using Python and Boto3.
* Automated deletion of unused EBS snapshots.
* Gained hands-on experience with AWS resource management and automation.

---

## Author

**Preetham Thyagarthy S**

