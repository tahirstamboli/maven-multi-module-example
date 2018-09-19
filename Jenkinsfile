node {
	stage("checkout"){
		checkout scm
	}

	stage("build"){
		mvn 'clean install -DskipTests=true -Dmaven.javadoc.skip=true -Dcheckstyle.skip=true -B -V'
	}

	def mvn(args) {
	    withMaven(
		// Maven installation declared in the Jenkins "Global Tool Configuration"
		maven: 'Maven 3.x',
		// Maven settings.xml file defined with the Jenkins Config File Provider Plugin
		
		// settings.xml referencing the GitHub Artifactory repositories
		 mavenSettingsConfig: '0e94d6c3-b431-434f-a201-7d7cda7180cb',
		// we do not need to set a special local maven repo, take the one from the standard box
		//mavenLocalRepo: '.repository'
		) {
		// Run the maven build
		sh "mvn $args -Dmaven.test.failure.ignore"
	    }
	}
}
