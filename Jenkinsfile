def label = 'k8s-runner'

podTemplate(
    label: label,
    containers: [
        containerTemplate(
            name: 'jnlp',
            image: 'synology:6000/jenkins-agent:latest',
            workingDir: '/home/jenkins',
        )
    ],
    volumes: [
        hostPathVolume(hostPath: '/usr/bin/docker', mountPath: '/usr/bin/docker'),
        hostPathVolume(hostPath: '/var/run/docker.sock', mountPath: '/var/run/docker.sock')
    ]
) {
    node(label) {

        def myRepo = checkout scm

        stage('Hello') {
          echo 'Hello Sweden'
        }
    }
}
