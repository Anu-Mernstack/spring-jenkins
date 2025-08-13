stage('Run') {
    steps {
        bat '''
        for %%f in (target\\*.jar) do (
            start /B java -jar "%%f" --server.port=9090
        )
        '''
    }
}
