# pipelines-autoscaling

oc new-project dev --display-name="Tasks - Dev" <br/>
oc new-project cicd --display-name="CI/CD" <br/>
oc policy add-role-to-group edit system:serviceaccounts:cicd -n dev <br/>
add jenkins ephemeral to dev project <br/>
add nodejs6 imagestream in openshift namespace <br/>

Clone this git repo. Navigate to the directory where you have cicd-template.yaml Then oc new-app -n cicd -f cicd-template.yaml <br/> 

oc set triggers bc/tasks-pipeline --from-github <br/>
oc describe bc/tasks-pipeline <br/>


ab -n 100 -c 10 "nodejs routename in dev namespace" <br/>
