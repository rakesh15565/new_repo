pipeline{
    agent any
    stages{
        stage("cloning"){
            steps{
                    git url:"https://github.com/rakesh15565/new_repo.git",branch:"main"
            }
        }
        stage("dependency"){
            steps{
                bat '''
                    python -m venv venv
                    call venv\\Scripts\\activate
                    pip install --upgrade pip
                    pip install pytest
                '''

            }
        }
        stage("test"){
            steps{
                bat '''
                    call venv\\Scripts\\activate
                    pytest test.py
                '''
            }
        }
        stage("deploy"){
            steps{
                bat '''
                    call venv\\Scripts\\activate
                    python add.py
                '''
            }
        }
    }
}