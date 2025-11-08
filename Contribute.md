## Manual installation
    - Install nodejs locally
    - Clone the repo
    - Install dependencies (npm install)
    - Start the DB locally
        - docker run -e PSTGRES_PASSWORD=mysecretpassword
        - Go to neon.tech or supabase and get yourself a new database
    - Change the .env file and update your db credentials
    - npx prisma migrate
    - npx prisma generate
    - npm run build
    - npm run start

## Docker Installation
    - Install docker 
    - Create a network - `docker network create user_project`
    - Start the postgres
        - docker run --name user-postgres-app --network user_project -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres
    - Build the image - `docker build --network=host -t user-project .`
    - Start the image - `docker run --network user_project -e DATABASE_URL=postgresql://postgres:mysecretpassword@user-postgres-app:5432/postgres -p 3000:3000 user-project`
        
## Docker Compose Installation
    - Install docker, docker-compose
    - Run `docker-compose up`