podTemplate(
  label: jenkins-slave-2,
  containers: [
    containerTemplate(name: 'jnlp', image: 'synology:6000/inbound-agent:latest', args: '${computer.jnlpmac} ${computer.name}')
  ]
) {
    node('jenkins-slave-2') {

        def myRepo = checkout scm

        stage('Hello') {
          echo 'Hello Sweden'
        }
    }
}
