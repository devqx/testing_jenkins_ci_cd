
node('master'){
    try {
        stage('build'){
            checkout scm
            // Install dependencies, create .env file and generate key for testing
            sh "composer install"
            sh "mv example .env"
            sh "php artisan key:generate"
        }

        stage('test'){
            sh "./vendor/bin/phpunit"
        }
        stage('deploy'){
            sh "echo WE ARE DEPLOYING"
        }
    }
    catch(error){
        throw error
    }
    finally {

    }
}
