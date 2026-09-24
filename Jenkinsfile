pipeline {
    agent any
    environment
    {
        BUILD_TOOL="C:\\Users\\HP\\AppData\\Local\\Keil_v5\\UV4\\UV4.exe"
        PRJ="D:\\03_WABCO_MOTIX\\00_Source_Code\\TLE989x_FOC_BASIC_Sensorless_Example\\FOC.uvprojx"
        BUILD_LOG="Build_log.txt"
    }
    stages
    {
        stage('Pre-Checks')
        {
            steps
            {
                bat '''
                echo 'Printing variables'
                echo %BUILD_TOOL%
                echo %PRJ%
                '''
            }
        }

        stage ('Build Project')
        {
            steps
            {
                /*Clean and Build Project*/
                bat '''
                echo 'Cleaning %PRJ%
                %BUILD_TOOL% -c %PRJ%
                echo 'Building Project'
                %BUILD_TOOL% -b %PRJ% -o %BUILD_LOG%

                '''
            }
        }
        stage('Test Stage')
        {
            parallel
            {
                stage('Static Analysis')
                {
                    steps
                    {
                    bat 'echo running Static tests' 
                    }
                    post
                    {
                        success
                        {
                        bat 'echo Completed Static Testing'
                        }
                    }
                }
                stage('Unit Test')
                {
                    steps
                    {
                    bat 'echo running Unit tests' 
                    }
                    post
                    {
                        success
                        {
                        bat 'echo Completed Static Testing'
                        }
                    }
                }
                stage('Integration Test')
                {
                    steps
                    {
                    bat 'echo running Integration tests' 
                    }
                    post
                    {
                        success
                        {
                        bat 'echo Completed Static Testing'
                        }                    }
                }
                stage('Qualification Tests')
                {
                    steps
                    {
                    bat 'echo running Qualification tests' 
                    }
                    post
                    {
                        success
                        {
                        bat 'echo Completed Static Testing'
                        }                    }
                }
            }
        }
    }
}