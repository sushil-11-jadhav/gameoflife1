pipeline {
        agent {
                label {
                        label "slave1"
                        customWorkspace "/mnt/ccc"
                }
        }
        stages {
                stage ("packaging") {
                                    steps {
                                            sh "mvn clean install"
                                    }
                }
                stage ("copy to tomcat") {
                                    steps {
                                            sh "cp gameoflife-web/target/gameoflife.war /mnt/apache-tomcat-9.0.74/webapps/"
                                        }
                }
                stage ("started tomcat") {
                                    steps {
                                            sh "sh /mnt/apache-tomcat-9.0.74/bin/startup.sh"
                                    }
                }
        }
}
