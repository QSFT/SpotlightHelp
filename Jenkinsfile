def sharedLib = library('f1-shared-library').com.lib
timestamps
{
    nodeWithProperWorkspace('VS2017ForSoSSE131', 'SE')
    {
        stage 'Prepare'
            bat "RD /S /Q . > nul || echo bypass error" 
    		bat 'md OnlineHelp | exit /b 0'
    		def CurrentDir=pwd()
        stage 'Checkout SpotlightHelp'
            dir("${CurrentDir}/OnlineHelp") {
				checkout scm
			}
        stage 'Build SpotlightHelp'
            dir("${CurrentDir}/OnlineHelp") {
                def buildhelp = load("_build/BuildHelp.groovy")
				buildhelp.BuildHelp()
            }
        stage 'Upload to Artifactory'
            def zip = '"C:\\Program Files\\7-Zip\\7z.exe"'
            dir("${CurrentDir}/OnlineHelp") { 
                bat """${zip} a ${CurrentDir}\\OnlineHelp\\OnlineHelp.zip ${CurrentDir}\\OnlineHelp\\_install"""
				bat """${zip} a ${CurrentDir}\\OnlineHelp\\OnlineHelp.zip ${CurrentDir}\\OnlineHelp\\_site"""
				bat """${zip} a ${CurrentDir}\\OnlineHelp\\OnlineHelp.zip ${CurrentDir}\\OnlineHelp\\_siteBalloonHelp"""
				
				Jfrog = sharedLib.Jfrog.new(this);
				def branchName = env.BRANCH_NAME;
				def uploadPattern = "OnlineHelp.zip"
				Jfrog.uploadSpotlightHelp(branchName, uploadPattern)
            }
    }
}

void nodeWithProperWorkspace(def slave, def space, def body) {
    node (slave) {
        ws(space) {
            body.call()
        }
    }
}
