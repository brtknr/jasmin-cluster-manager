# JASMIN Cluster Manager

## Clone repository:

	git clone git@github.com:cedadev/jasmin-cluster-manager.git
	cd jasmin-cluster-manager

## Create AWX node:

	virtualenv venv
	source venv/bin/activate
	pip install -r requirements.txt
	openstack stack create cluster-manager -e example-heat-params.yml -t server.yml
	
Once the cluster is ready, obtain AWX admin password as follows:

	openstack stack output show cluster-manager awx_admin_password

## Create a Kubernetes cluster:

- On AWX web portal, navigate to `Credentials` panel and create `JASMIN Cloud
  User` type credential using your JASMIN OpenStack credentials.
- Navigate to `Templates` panel and launch the `Kubernetes` template (using the
  rocket icon).
- Select `Kubernetes Example Inventory` inventory type, followed by your
  `JASMIN Cloud User` credential, complete the survey as necessary and launch
  the cluster creation job.

## Install galaxy roles locally:

	ansible-galaxy install -r roles/requirements.yml -p roles/
