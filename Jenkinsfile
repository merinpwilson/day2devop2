// pipeline {
//     agent any

//     environment {
//         IMAGE_NAME = "react-vite-app"
//         CONTAINER_NAME = "react-vite-container"
//     }

//     stages {

//         stage('Clone Code') {
//             steps {
//                 git branch: 'main',
//                     url: 'https://github.com/MamthaKSunilkumar/CS8_demo.git'
//             }
//         }

//         stage('Build Docker Image') {
//             steps {
//                 bat 'docker build -t $IMAGE_NAME .'
//             }
//         }

//         stage('Stop Old Container') {
//             steps {
//                 bat '''
//                 docker stop $CONTAINER_NAME || true
//                 docker rm $CONTAINER_NAME || true
//                 '''
//             }
//         }

//         stage('Run Docker Container') {
//             steps {
//                 bat '''
//                 docker run -d \
//                 -p 5173:5173 \
//                 --name $CONTAINER_NAME \
//                 $IMAGE_NAME
//                 '''
//             }
//         }
//     }

//     post {
//         success {
//             echo 'React app deployed using Docker successfully 🎉'
//         }
//         failure {
//             echo 'Deployment failed ❌'
//         }
//     }
// }
pipeline {
    agent any

    environment {
        IMAGE_NAME = "welcom-react"
        CONTAINER_NAME = "clever_galois"
    }

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/merinpwilson/day2devop2.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh '''
                docker stop $CONTAINER_NAME || true
                docker rm $CONTAINER_NAME || true
                '''
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                docker run -d -p 5173:5173 --name $CONTAINER_NAME $IMAGE_NAME
                '''
            }
        }
    }

    post {
        success {
            echo 'React app deployed using Docker successfully 🎉'
        }
        failure {
            echo 'Deployment failed ❌'
        }
    }
}
