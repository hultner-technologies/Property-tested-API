.PHONY: install run run-dev test

install:
	poetry install

run:
	(cd src/user_api; uvicorn main:app)


run-dev:
	(cd src/user_api; poetry run uvicorn main:app --reload)


test:
	poetry run schemathesis run -c all -w 16 --hypothesis-max-examples=100 --hypothesis-verbosity normal  "http://127.0.0.1:8000/openapi.json"
	poetry run pytest
