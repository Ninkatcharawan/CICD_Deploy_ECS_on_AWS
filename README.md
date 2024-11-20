## CI/CD Pipeline Steps

### Detailed Steps

1. **Source Code Commit**  
   The pipeline begins when code is pushed to a repository (e.g., AWS CodeCommit, GitHub, or Bitbucket).

2. **CodeBuild: Build Docker Image**
   - **Step 1:** Pull source code from the repository.  
   - **Step 2:** Install dependencies (defined in `buildspec.yml`).  
   - **Step 3:** Run tests (optional).  
   - **Step 4:** Build the Docker image.  
   - **Step 5:** Authenticate to Amazon ECR.  
   - **Step 6:** Push the Docker image to ECR.

3. **Amazon ECR: Store Docker Image**
   - **Step 7:** Store the Docker image with a specific tag (e.g., `latest` or versioned).  

4. **CodeDeploy: Deploy to ECS**
   - **Step 8:** Fetch the updated Docker image from ECR.  
   - **Step 9:** Update the ECS Task Definition with the new Docker image.  
   - **Step 10:** Deploy the new Task Definition to the ECS Service.  
   - **Step 11:** ECS starts new containers with the updated Docker image.  
   - **Step 12:** ECS stops old containers (if successful).

5. **Amazon ECS: Running the Application**
   - **Step 13:** The ECS Cluster runs updated containers.

---

### How to Update Your GitHub Repository

1. **Create/Edit README.md**: If you're updating the README file, open it in your code editor.
2. **Copy the Above Content**: Paste the Markdown content (formatted steps) in your README or a new file.
3. **Commit Changes**:
   ```bash
   git add README.md
   git commit -m "Updated CI/CD pipeline steps"
   git push origin main
   ```
4. **Verify on GitHub**: Open your repository on GitHub to ensure the updated steps are displayed correctly.
