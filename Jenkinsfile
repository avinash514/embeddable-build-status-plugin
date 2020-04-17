def BuildBadge = addEmbeddableBadgeConfiguration(id: "buildbadge", subject: "Embeddable Build Status")

pipeline {
    agent any
    stages {
        stage('Embeddable Build Status.'){
        steps {
            script {
                println "This is Embeddable Build Status Plugin Test"
                println "This is PR Hook Test"
                println "${ghprbPullId}"
                
                BuildBadge.setStatus('running')
                try {
                    //RunBuild()
                    BuildBadge.setStatus('passing')
                } catch (Exception err) {
                    BuildBadge.setStatus('failing')

                    /* Note: If you do not set the color
                             the configuration uses the best status-matching color.
                             passing -> brightgreen
                             failing -> red 
                             ...
                    */
                    BuildBadge.setColor('pink')

                    error 'Build failed'
                }
            }
        }
        }
    }
}
