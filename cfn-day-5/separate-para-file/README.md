https://stackoverflow.com/questions/45749424/passing-multiple-parameters-from-external-file-to-cloudformation-template-and-us

https://docs.aws.amazon.com/cli/latest/reference/cloudformation/create-stack.html

aws cloudformation create-stack --stack-name dev-network-infra-pf --template-body file://infra-network.yaml --parameters file://dev-para-file.json

aws cloudformation delete-stack --stack-name myteststack


NOTE: 

We can **pass the values in the yaml file directly** and then cregate from the console

We can also **use the actual yaml file and the parameter store to store the value**. then, create the stack from the console

**Parameter file**: here we have the yaml file, parameter.json file, and then use aws cli reference to orchestrate the deplyment and create the stack from the CLI e.g. aws cloudformation create-stack --stack-name dev-network-infra-pf --template-body file://infra-network.yaml --parameters file://dev-para-file.json

Separate Parameter file**Parameter file.json + yaml file + PS**, using CLI commands: We can also use parameter store, parameter file.json and the actual yaml file by passing the parameter keyname from SSM PS in the json file where it is asking for parameter value. CFN will travel to PS to consume the value. Here, the same CLI code will be used as well to cregate the stack from the cli. Parameter file can be used with other CI tools as well like Jenkins, codeBuild, using the cli command etc







