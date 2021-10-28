.PHONY: help

help:
	@grep -E '^[a-zA-Z0-9_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'
	@printf "Default variables (overridable):\n"
	@printf "  - root_pass: root\n"
	@printf "  - user_login: admin\n"
	@printf "  - user_pass: password\n"
	@printf "  - db_name: admin\n"

net_base_name = net_postgres
user_login = 'admin'
user_pass = 'password'
db_name = 'admin'

# PostgreSQL latest
latest-up: ## Create new podman container with postgres latest image
	podman network create ${net_base_name}_latest
	podman run --name postgres_latest -d \
 					-e POSTGRES_USER=${user_login} \
 					-e POSTGRES_PASSWORD=${user_pass} \
 					-e POSTGRES_DB=${db_name} \
 					-p 5432:5432 postgres:14-alpine
latest-down: ## Stop and remove postgres latest container
	podman stop postgres_latest
	podman rm postgres_latest
	podman network rm ${net_base_name}_latest

# PostgreSQL 14
14-up: ## Create new podman container with postgres 14 image
	podman network create ${net_base_name}_14
	podman run --name postgres_14 -d \
 					-e POSTGRES_USER=${user_login} \
 					-e POSTGRES_PASSWORD=${user_pass} \
 					-e POSTGRES_DB=${db_name} \
 					-p 5432:5432 postgres:14-alpine
14-down: ## Stop and remove postgres 14 container
	podman stop postgres_14
	podman rm postgres_14
	podman network rm ${net_base_name}_14

# PostgreSQL 13
13-up: ## Create new podman container with postgres 13 image
	podman network create ${net_base_name}_13
	podman run --name postgres_13 -d \
 					-e POSTGRES_USER=${user_login} \
 					-e POSTGRES_PASSWORD=${user_pass} \
 					-e POSTGRES_DB=${db_name} \
 					-p 5432:5432 postgres:13-alpine
13-down: ## Stop and remove postgres 13 container
	podman stop postgres_13
	podman rm postgres_13
	podman network rm ${net_base_name}_13

# PostgreSQL 12
12-up: ## Create new podman container with postgres 12 image
	podman network create ${net_base_name}_12
	podman run --name postgres_12 -d \
 					-e POSTGRES_USER=${user_login} \
 					-e POSTGRES_PASSWORD=${user_pass} \
 					-e POSTGRES_DB=${db_name} \
 					-p 5432:5432 postgres:12-alpine
12-down: ## Stop and remove postgres 12 container
	podman stop postgres_12
	podman rm postgres_12
	podman network rm ${net_base_name}_12

# PostgreSQL 11
11-up: ## Create new podman container with postgres 11 image
	podman network create ${net_base_name}_11
	podman run --name postgres_11 -d \
 					-e POSTGRES_USER=${user_login} \
 					-e POSTGRES_PASSWORD=${user_pass} \
 					-e POSTGRES_DB=${db_name} \
 					-p 5432:5432 postgres:11-alpine
11-down: ## Stop and remove postgres 11 container
	podman stop postgres_11
	podman rm postgres_11
	podman network rm ${net_base_name}_11
