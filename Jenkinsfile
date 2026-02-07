pipeline {
    agent any

    stages {

        stage('Install Nginx') {
            steps {
                sh '''
                if ! command -v nginx >/dev/null; then
                  sudo apt update
                  sudo apt install -y nginx
                fi
                '''
            }
        }

        stage('Deploy Website') {
            steps {
                sh '''
                echo "Deploying static website..."

                sudo rm -rf /var/www/html/*

                # copy html and css
                sudo cp cloud-kitchen/index.html /var/www/html/
                sudo cp cloud-kitchen/styles.css /var/www/html/

                # copy images folder
                sudo cp -r images /var/www/html/

                sudo chown -R www-data:www-data /var/www/html
                sudo chmod -R 755 /var/www/html

                sudo systemctl restart nginx
                '''
            }
        }
    }

    post {
        success {
            sh '''
            echo "====================================="
            echo " Website deployed successfully 🎉"
            echo " Access URL: http://3.80.81.18"
            echo "====================================="
            '''
        }
    }
}
