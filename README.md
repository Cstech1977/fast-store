# commands uv
- uv init
- uv init --app services/<service-name>
- uv add "fastapi[standard]" --package user-service
- uv run --package user-service fastapi dev services/user-service/main.py --port 8001
- uv add sqlmodel --package user-service
- uv add "psycopg[binary]" --package user-service
- uv add "passlib[bycrypt]" --package user-service
- uv add pyjwt fastapi
- uv init --app services/order-service 

## commands docker
- docker compose up --build
- docker compose down

### commands grpc
- uv run python -m grpc_tools.protoc -I protos
--python_out=services/product-service
--grpc_python_out=services/product-service protos/product.proto

#### commands git
- git init
- git add .
- git commit -m "Primeiro commit"
- gh repo create nome-do-repositorio --public --source=. --push


