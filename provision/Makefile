
.PHONY: lint setup play help

.DEFAULT_GOAL := help

galaxy: ## Install roles from ansible galaxy
	ansible-galaxy install -r requirements.yml

lint: ## Lints the ansible playbook
	ansible-lint setup.yml tasks

setup: ## Run initial setup script
	sh setup.sh

play: ## Runs the main playbook
	ansible-playbook setup.yml --ask-become-pass -i hosts

help: ## Display this help screen
	@grep -h -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'