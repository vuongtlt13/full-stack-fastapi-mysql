start-infra:
	cd .. && docker compose up -d

stop-infra:
	docker compose down

# usage: make migration-generate <filename>
migration-generate:
	alembic revision --autogenerate -m "$(word 1, $(filter-out $@,$(MAKECMDGOALS)))"

migrate-up:
	alembic upgrade head

db-seed:
	uv run python -m app.initial_data