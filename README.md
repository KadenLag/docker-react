## Docker Commands ##

# docker run -p 3000:3000 -v /app/node_modules -v $(pwd):/app 6786dfcfd699
-v /app/node_modules (sets to not use or bookmark), -v $(pwd):/app references
current working parth to working directory app. : colon means outside container.
ports are your machine then dockers image port

# docker exec -it 90f730a04b97 npm run test
exec a test suite inside the currently running compose

#  tests:
    build:
      context: .
      dockerfile: Dockerfile.dev
    volumes:
      - /app/node_modules
      - .:/app
    command: ["npm", "run", "test"]
extra service for tests but cannot interact with it. use the exec to interact