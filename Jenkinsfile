pipeline{
    agent any
    stages{
        stage("Creating AWS EKS Cluster"){
            steps{
                 echo "========Creating AWS EKS Cluster========"
                 sh ''' eksctl create cluster --name EKSUdacityCapstone-01
                         --nodegroup-name linux-nodes 
                         --node-type t2.micro 
                         --nodes 2 
                         --ssh-access 
                         --ssh-public-key=ssh-jump-box
                     '''
            }
            post{
                success{
                    echo "========EKS cluster created successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
    }
}