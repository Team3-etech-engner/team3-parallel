pipeline{
	agent any
		stages{
			stage('git-clone'){
				steps{
					checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/Team3-etech-engner/team3-parallel.git']]])
				}
			}
			stage('parallel-level'){
				parallel {
					stage('sub-job1'){
						steps{
							echo "sub-job1 task"
						}
					}
					stage('sub-job2'){
						steps{
							echo "sub-job2 task"
						}
					}
                    stage('user-check'){
                        steps{
                            echo "sub-job3"
                        }
                    }
				}
			}
			stage('version-check'){
				steps{
					echo  "end of parallel job"
				}
			}
		}
}