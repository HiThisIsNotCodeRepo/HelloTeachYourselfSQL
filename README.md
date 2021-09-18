# HelloTeachYourselfSQL

> This is for personal study note of *Sams Teach Yourself SQL in 10 Minutes*
>
> [Credit](https://forta.com/books/0672336073/)

*Setup PostgreSQL*

1. `docker run --name my-postgres -p 5432:5432 -e POSTGRES_PASSWORD=password -d postgres`
2. `docker exec -it my-postgres psql -U postgres -d postgres`
3. `create database tysql;`
4. `\l`