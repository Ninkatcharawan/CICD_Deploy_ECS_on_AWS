# CICD_Deploy_ECS_on_AWS

Start
  |
  ▼
Source Code Commit (AWS CodeCommit / GitHub / Bitbucket)
  |
  ▼
CodeBuild (Build Docker Image)
  ├── Step 1: Pull source code from repository
  ├── Step 2: Install dependencies (defined in buildspec.yml)
  ├── Step 3: Run tests (optional)
  ├── Step 4: Build Docker image
  ├── Step 5: Authenticate to Amazon ECR
  └── Step 6: Push Docker image to ECR
  |
  ▼
Amazon ECR (Image Repository)
  └── Step 7: Store Docker image with a specific tag (e.g., latest or versioned)
  |
  ▼
CodeDeploy (Deploy to ECS)
  ├── Step 8: Fetch updated Docker image from ECR
  ├── Step 9: Update ECS Task Definition with new Docker image
  ├── Step 10: Deploy new Task Definition to ECS Service
  ├── Step 11: ECS starts new containers with updated Docker image
  └── Step 12: ECS stops old containers (if successful)
  |
  ▼
Amazon ECS (Running the Application)
  └── Step 13: ECS Cluster runs updated containers
  |
  ▼
End
