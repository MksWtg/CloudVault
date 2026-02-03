
- Earlier last year I spent some time working on document utility fixes
- The document utility tool was built as a supplementary tool for eDoc migration in the context of the Ceph -> S3 migrations that were conducted from 2023-2025
	- The migrations moved docs from Ceph to S3
	- This tool pulls doc from S3 to local DB (rehydrates local DB)
- Since the process that the tool does requires a specific set of infrastructure to work (the CW ecosystem, DBs, registry), functional testers need to understand this so they can recreate it locally
- I have documented setup from start to finish so other product team members that wish to functionally test can functionally test any Doc Util changes
- Can access current notes here: https://github.com/WiseTechGlobal/CargoWise.DocumentUtility/pull/44