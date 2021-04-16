DOCKER ?= docker
DOCKER_REGISTRY := asia.gcr.io/tbd
DOCKER_DIR := ./build/docker

MOCKGEN ?= mockgen

GQLGEN ?= gqlgen
GQL_SCHEMA_DIR ?= ./graph

GO ?= go
GOLINT ?= golint
GO_ENV ?= GOBIN=$(BIN)
GOOS := $(shell $(GO) env GOOS)
GOARCH := $(shell $(GO) env GOARCH)
BIN := $(abspath ./bin/$(GOOS)_$(GOARCH))

$(BIN)/gqlgen:
	$(GO_ENV) $(GO) install -mod=mod github.com/99designs/gqlgen@v0.13.0

.PHONY: lint-gql
lint-gql:

.PHONY: format-gql
format-gql:
	format-graphql --write true $(GQL_SCHEMA_DIR)/schema.graphqls


