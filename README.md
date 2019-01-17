# JASMIN Cluster Manager

## Clone repository:

	git clone git@github.com:cedadev/jasmin-cluster-manager.git
	cd jasmin-cluster-manager

## Create AWX node:

	virtualenv venv
	source venv/bin/activate
	pip install -r requirements.txt
	openstack stack create cluster-manager -e example-heat-params.yml -t server.yml

## Install galaxy roles locally:

	ansible-galaxy install -r roles/requirements.yml -p roles/
