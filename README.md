## My Project
HTCondor Baseline

**Introduction**
HTCondor is a robust workload management system for distributed computing. This project integrates HTCondor with Amazon Web Services (AWS), leveraging cloud resources for scalable and efficient high-throughput computing tasks.

The CloudFormation templates provided in this project are designed to simplify and automate the deployment of HTCondor in AWS. They create two key components:

Access Point (AP) Stack: This sets up the "master" node of the HTCondor cluster. The Access Point is responsible for managing the overall state of the system and distributing workloads.

Execution Point (EP) Stack: This creates the "worker" nodes of the cluster. The Execution Points are responsible for performing the actual jobs and tasks assigned by the Access Point.

This architecture follows a common pattern in distributed systems, with a central control plane (the Access Point) managing the overall state and coordinating work, while individual worker nodes (the Execution Points) focus on executing tasks. This division of responsibilities helps to scale the system and improve overall efficiency and reliability.


**Key features:**

Scalable computing resources
Cost-efficient pay-as-you-go model
Flexible access to diverse AWS instance types
Enhanced reliability and fault tolerance
Prerequisites
AWS account
Basic understanding of AWS services
Familiarity with CloudFormation
Knowledge of EC2 and IAM


**Setup**
Configure Instance Metadata Service (IMDS) defaults in AWS EC2.
Create an EC2 Keypair.
Launch the Access Point (AP) Stack using the provided CloudFormation template.
Launch the Execution Point (EP) Stack using the provided CloudFormation template.
Set up the HTCondor Annex.
Detailed instructions for each step are provided in the full documentation of HTCCondorInstructions.txt.

**Usage**
After setup, you can use HTCondor to manage and run your distributed computing tasks in AWS.

**Basic commands:**    
condor_submit <job_file>
condor_q
condor_status

        
**Testing**
Create test scripts (sleep.sh and sleep.sub).
Submit test jobs:
    
condor_submit sleep.sub

    

    
Check job status:
    
condor_q

    

    
**Best Practices**
Leverage Spot Instances for cost savings.
Optimize instance types for your workloads.
Use Reserved Instances and Savings Plans for predictable workloads.
Monitor and continuously adjust compute selection using AWS Cost Explorer, CloudWatch, and Compute Optimizer.


**Cleanup**
To avoid ongoing costs, clean up resources when finished:

Delete the Execution Point (EP) Stack.
Deregister the associated Amazon Machine Image (AMI).
Delete the snapshot used to create the AMI.
Contributing
Contributions to improve the project are welcome. Please follow the standard GitHub pull request process.

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

