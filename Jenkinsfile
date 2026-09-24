pipeline {
    agent any
    environment
    {
        BUILD_TOOL="C:\\Users\\HP\AppData\\Local\\Keil_v5\\UV4\\UV4.exe"
        PRJ="D:\\03_WABCO_MOTIX\\00_Source_Code\\TLE989x_FOC_BASIC_Sensorless_Example\\FOC.uvprojx"
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
    }
}