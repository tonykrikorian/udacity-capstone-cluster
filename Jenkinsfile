pipeline{
    agent any
    stages{
        stage("Create EKS Cluster"){
            steps{
                echo "========Creating AWS EKS Cluster========"
                sh ''' eksctl create cluster --name EKSUdacityCapstone  
                    --version 1.17 
                    --region us-west-2 
                    --nodegroup-name linux-nodes 
                    --node-type t2.micro --nodes 2 
                    --ssh-access --ssh-public-key=ssh-jump-box 
                    --tags Description="Udacity Capstone EKS Cluster" Name="EKSUdacityCapstone" 
                    '''
            }
        }
    }
    
}