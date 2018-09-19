node {
	stage("checkout"){
		checkout scm
	}

	stage("build"){
		sh "mvn clean install -DskipTests=true -Dmaven.javadoc.skip=true -Dcheckstyle.skip=true -B -V"
	}
	
	stage("unit tests"){
		sh "mvn test -Dmaven.javadoc.skip=true -Dcheckstyle.skip=true -B -V"
	}

}
