.PHONY: help

help:
	@grep -E '^[a-zA-Z0-9_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'
	@printf "Default variables (overridable):\n"
	@printf "  - root_pass: root\n"
	@printf "  - user_login: admin\n"
	@printf "  - user_pass: password\n"
	@printf "  - db_name: admin\n"

net_base_name = net_mariadb
root_pass = 'root'
user_login = 'admin'
user_pass = 'password'
db_name = 'admin'

latest-up: ## Create new podman container with mariadb latest image
	podman network create ${net_base_name}_latest
	podman run --name mariadb_latest -d \
					-e MARIADB_ROOT_PASSWORD=${root_pass} \
					-e MARIADB_DATABASE=${db_name} \
					-e MARIADB_USER=${user_login} \
					-e MARIADB_PASSWORD=${user_pass} \
					-p 3306:3306 mariadb:latest

latest-down: ## Stop and remove mariadb latest container
	podman stop mariadb_latest
	podman rm mariadb_latest
	podman network rm ${net_base_name}_latest

10-up: ## Create new podman container with mariadb 10 image
	podman network create ${net_base_name}_10
	podman run --name mariadb_10 -d \
						-e MARIADB_ROOT_PASSWORD=${root_pass} \
						-e MARIADB_DATABASE=${db_name} \
						-e MARIADB_USER=${user_login} \
						-e MARIADB_PASSWORD=${user_pass} \
						-p 3306:3306 mariadb:10

10-down: ## Stop and remove mariadb 10 container
	podman stop mariadb_10
	podman rm mariadb_10
	podman network rm ${net_base_name}_10
