pipeline {
	agent any
	stages {
		stage("build") {
			when {
				expression	{
					env.GIT_BRANCH == 'origin/main'
				}
			}
			steps {
				echo 'building the applicaiton...'
			}
		}
		stage("test") {
			when {
				expression	{
					env.GIT_BRANCH == 'origin/main' || env.GIT_BRANCH == ''
				}
			}
			steps {
				echo 'testing the applicaiton...'
			}
		}
		stage("deploy") {
			steps {
				echo "${env.GIT_BRANCH}"
				echo 'deploying the applicaiton...'
			}
		}
	}
	post	{
		always	{
			echo "building..."
		}
		success	{
			echo "success"
		}
		failure	{
			echo "failure"
		}
	}
}