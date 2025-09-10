pipeline {
    agent any

    environment {
        REGISTRY = "docker.io/laxmi007"   // replace with your Docker Hub username
        FRONTEND_IMAGE = "${REGISTRY}/chattingo-frontend"
        BACKEND_IMAGE  = "${REGISTRY}/chattingo-backend"
        IMAGE_TAG = "v${BUILD_NUMBER}"             // version tag based on Jenkins build number
    }

    stages {
        stage('Git Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/laxmishiwarkar1997/chattingo.git'
            }
        }

        stage('Image Build') {
           steps {
        // scan the workspace (your source code) for vulnerabilities
        sh "trivy fs --exit-code 0 --severity CRITICAL,HIGH . > trivy-fs-report.txt || true"
        sh "cat trivy-fs-report.txt"
        }
        }

        stage('Filesystem Scan') {
            steps {
                sh 'echo "Filesystem scan placeholder (Trivy/Checkov/etc.)"'
            }
        }

        stage('Image Scan') {
            steps {
                sh "trivy image ${FRONTEND_IMAGE}:${IMAGE_TAG} || true"
                sh "trivy image ${BACKEND_IMAGE}:${IMAGE_TAG} || true"
            }
        }

        stage('Push to Registry') {
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
                        sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
                        sh "docker push ${FRONTEND_IMAGE}:${IMAGE_TAG}"
                        sh "docker push ${BACKEND_IMAGE}:${IMAGE_TAG}"
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                docker compose down
                docker compose up -d --build
                '''
            }
        }
    }
}
