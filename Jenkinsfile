podTemplate(
  label: 'jenkins-slave-2',
  containers: [
    containerTemplate(
      name: 'jnlp',
      image: 'synology:6000/inbound-agent:latest'
    )
  ]
) {
    node('jenkins-slave-2') {

        def myRepo = checkout scm

        stage('Hello') {
          echo 'Hello Sweden'
          sh "uname -m"
        }

	def slackResponse = slackSend color: "danger", message: "Fucking failure"
	slackResponse.addReaction("thumbsup")
    }
}
