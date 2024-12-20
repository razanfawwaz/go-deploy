## Usage

To run the server locally, use the following command:

```bash
go run main.go
```

The server will start on port 8080. You can access it by navigating to `http://localhost:8080` in your web browser.

## Deployment

This project includes a GitHub Actions workflow for automated deployment. The workflow is triggered on pushes to the `main` branch. It builds the Go binary and deploys it to a remote server using SSH.

### Steps in the Workflow:

1. **Checkout code**: Retrieves the latest code from the repository.
2. **Set up Go**: Configures the Go environment.
3. **Build binary**: Compiles the Go application for Linux.
4. **Stop service**: Stops the existing service on the server.
5. **Copy Binary File to Server**: Transfers the built binary to the server.
6. **Restart service**: Restarts the service to apply the new changes.

Make sure to set the following secrets in your GitHub repository for the deployment to work:

- `SERVER_IP`: The IP address of your server.
- `SERVER_USER`: The username for SSH access.
- `SSH_PRIVATE_KEY`: The private key for SSH authentication.

