# jenkins-image
#### build image
`$ docker image build -t jenkins-app -f Dockerfile .`

#### run image
`$ docker run --name my-jenkins -d -v /var/run/docker.sock:/var/run/docker.sock -v $(which docker):/usr/bin/docker -v ${PWD}/jenkins_home:/var/jenkins_home -p 8080:8080 -p 50000:50000 jenkins-app`

#### chmod docker for user jenkins
`$ docker exec -u 0 my-jenkins chmod 666 /var/run/docker.sock`
