name: Deploy

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@main

    - uses: kalmukvitaly/deploy-action@main
      name: Docker-Compose Remote Deployment
      with:
        ssh_host: ${{ secrets.SSH_HOST }}
        ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
        ssh_user: ${{ secrets.SSH_USER }}
        project_name: ProjectName
