# Building Packer image with GPC and Github Actions



## Use of GCP Workload Identity Federation
https://cloud.google.com/iam/docs/workload-identity-federation

Usecase: we are using Github Actions to build the packer image in the GCP cloud.
Till now we have been using service-account keys to authenticate with required permissions to create resource in cloud. 
PROBLEM: Use of services-account keys is extremely dangerous because the keys onces are compromised it would be extremely difficult to control them.
SOLUTION: Instead of using long lived service-account keys the best alternative is to use 
Workload Identity Federation. We will be using WIF to authenticate from Github Actions to GCP using shot-live token provided by WIF. 