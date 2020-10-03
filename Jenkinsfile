pipeline{
    agent any
    stages{
        stage("Creating AWS EKS Cluster"){
            steps{
                 echo "========Creating AWS EKS Cluster========"
                 sh ''' eksctl create cluster --name EKSUdacityCapstone-03
                         --region us-west-2
                         --nodegroup-name linux-nodes 
                         --node-type t2.micro 
                         --nodes 2 
                         --ssh-access 
                         --ssh-public-key=ssh-jump-box
                         --vpc-public-subnets=subnet-096985465aa5b0dc5,subnet-0d819e3e94f33ef10
                         --vpc-private-subnets=subnet-07a271886f736ad57,subnet-012a62844867021fc 
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