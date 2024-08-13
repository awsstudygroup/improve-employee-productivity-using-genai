### Product Description: Employee Productivity GenAI Assistant  🌌

**Employee Productivity GenAI Assistant ** is an AI-powered tool designed to boost productivity by automating the generation of documents, templates, and other written content. Tailored for users within the AWS ecosystem, this assistant utilizes Amazon Bedrock's generative AI models to create custom content based on user input, including text and images. The assistant is built on AWS's robust serverless technologies, ensuring scalability, high availability, and security. The product provides a user-friendly interface, allowing interaction with AI models for creating templates, naming products, and more, all while maintaining a comprehensive activity history for tracking and revisiting past interactions.

### Step-by-Step Guide to Deploy the Employee Productivity GenAI Assistant 

#### Pre-requisites 🛠️

1. **Miniconda:** Install Miniconda for managing Python environments, especially if using multiple Python versions.
2. **AWS CLI 2.x:** Install and authenticate the AWS CLI.
3. **AWS SAM CLI:** Required for deploying serverless applications.
4. **Linux Environment with Bash:** Use WSL on Windows or a native Linux environment.
5. **NodeJS:** Install NodeJS (version 16 or newer) for running the frontend.
6. **Python3:** Ensure Python 3.11 or newer is installed.
7. **jq:** Install jq for processing JSON on the command line.
8. **Bedrock Model Access:** Enable Claude models in the Amazon Bedrock console within the AWS region.

#### How to Deploy Locally 🚀

1. **Navigate to the project root directory.**
2. **Run the deployment script with the desired options:**
   - To deploy both backend and frontend:
     ```bash
     ./deploy.sh --region=your-aws-region --email=your-email
     ```
   - To deploy only the backend:
     ```bash
     ./deploy.sh --backend --region=your-aws-region --email=your-email
     ```
   - To deploy only the frontend:
     ```bash
     ./deploy.sh --frontend --region=your-aws-region --email=your-email
     ```
   - To delete the deployment:
     ```bash
     ./deploy.sh --delete --region=your-aws-region --email=your-email
     ```

3. **Wait for the deployment to complete.** This process will set up the necessary AWS resources and configure the application.

#### How to Deploy via AWS CloudShell ☁️

1. **Open AWS CloudShell.**
2. **Install necessary dependencies:**
   ```bash
   sudo yum groupinstall "Development Tools" -y && \
   sudo yum install openssl-devel bzip2-devel libffi-devel zlib-devel xz-devel ncurses-devel readline-devel sqlite-devel -y
   ```
3. **Install Python 3.11 using PyEnv:**
   ```bash
   git clone https://github.com/pyenv/pyenv.git ~/.pyenv
   echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bash_profile
   echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bash_profile
   echo 'eval "$(pyenv init -)"' >> ~/.bash_profile
   source ~/.bash_profile
   pyenv install 3.11
   pyenv global 3.11
   ```
4. **Create a working folder and clone the repository:**
   ```bash
   sudo mkdir /aws-samples && sudo chown cloudshell-user -R /aws-samples
   cd /aws-samples
   git clone https://github.com/awsstudygroup/improve-employee-productivity-using-genai
   cd improve-employee-productivity-using-genai/
   ```
5. **Deploy the backend:**
   ```bash
   ./deploy.sh --backend --region=your-aws-region --email=your-email
   ```
6. **Deploy the frontend:**
   ```bash
   ./deploy.sh --frontend --region=your-aws-region --email=your-email
   ```

#### How to Deploy via AWS Cloud9 ☁️

1. **Create a new Cloud9 environment:**
   - Choose `t3.medium` or larger instance type.
   - Use Amazon Linux 2023 as the platform.
   - Set the connection type to AWS System Manager (SSM).

2. **Prepare the Cloud9 environment:**
   - Open the IDE.
   - Clone the repository:
     ```bash
     git clone https://github.com/aws-samples/improve-employee-productivity-using-genai
     cd improve-employee-productivity-using-genai
     ```

3. **Deploy the application:**
   - Deploy both backend and frontend:
     ```bash
     ./deploy.sh --container --region=your-aws-region --email=your-email
     ```
   - Deploy only the backend:
     ```bash
     ./deploy.sh --backend --container --region=your-aws-region --email=your-email
     ```
   - Deploy only the frontend:
     ```bash
     ./deploy.sh --frontend --region=your-aws-region --email=your-email
     ```

#### Post Deployment Steps 🛠️

1. **Access the application via the CloudFront URL provided after deployment.**
2. **Sign in using the admin credentials provided.**
3. **Explore the features, including template creation and AI interactions.**
4. **Optionally, create additional users in the Cognito User Pool for broader access.**

#### Troubleshooting Tips

- **Check CloudFront deployment** if you encounter issues logging in.
- **Review environment variables** in `.env` and `aws-exports.json` if functionalities are missing.

This guide will help you deploy and start using the **Employee Productivity GenAI Assistant ** to enhance your document creation and productivity efforts.