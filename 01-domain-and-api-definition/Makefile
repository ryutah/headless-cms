help: ## Prints help for targets with comments
	@cat $(MAKEFILE_LIST) | grep -E '^[a-zA-Z_-]+:.*?## .*$$' | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'

.PHONY: oas_preview
oas_preview: ## Preview openapi definition
	docker run -p 8080:8080 -e SWAGGER_JSON=/api/openapi.yaml -v ${PWD}/api:/api swaggerapi/swagger-ui
