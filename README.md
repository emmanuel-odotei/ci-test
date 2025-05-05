# Payroll CI Test - Local Jenkins

This is a starter Jenkins CI setup for testing your smoke test scripts locally using Docker.

## Steps

1. Run Jenkins:
   ```
   docker compose up -d
   ```

2. Open Jenkins at [http://localhost:8080](http://localhost:8080)

3. Unlock using:
   ```
   docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
   ```

4. Create credential:
   - ID: `payroll_backend_staging_url`
   - Value: your GraphQL staging URL (e.g., `http://localhost:9000/graphql`)

5. Create a pipeline job and use the `Jenkinsfile` content.

6. Trigger build and watch logs.
