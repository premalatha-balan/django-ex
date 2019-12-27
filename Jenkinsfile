pipeline {
		agent any
		stages {
				stage ('Build') {
						steps {
							echo 'Running build phase'
						}

				}
				stage ('Two') {
						steps { 
								input('Do you want to proceed to Test stage? ')
								}

				}
				stage ('Three'){
							when {
									not {
									branch 'master'
									}
							}
							steps {
								echo 'Hello'
							}

				}
				stage("Four"){
						parallel{
								stage('Unit Test') {
													steps {
														echo 'Running Unit Tests'
													}
								}
								stage('Integration Test') {

													agent {
														docker {
																reuseNode false
																usage 'ubuntu'
														}
													}
													steps {
															echo 'Running the integration Tests'
													}
								}

						}

				}
				stage ('Monitor'){

				}
		}
}
