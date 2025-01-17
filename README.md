# AI Assistance API

AI Assistance API is a FastAPI-based application designed to provide **answers**, **step-by-step hints**, and **feedback** for educational purposes. The application leverages AWS Bedrock to interact with large language models, ensuring precise and efficient responses.

---

## Features

- **Get Answers**: Provides concise answers to user queries.
- **Generate Hints**: Produces step-by-step hints to guide users from basic to advanced concepts.
- **Provide Feedback**: Evaluates a user's input and returns constructive feedback.
- **AWS Bedrock Integration**: Uses Bedrock to interact with foundation models.

---

## Project Structure

```plaintext
ai_assistance/
│
├── core/
│   ├── __init__.py
│   ├── bedrock_client.py        # Handles Bedrock model interaction
│   └── s3_client.py             # (Optional) Handles S3 interactions for data storage
│
├── modules/
│   ├── ai_assistance/
│   │   ├── __init__.py
│   │   ├── processor.py         # Core AI assistance logic (answer generation, hints, feedback)
│   │   └── main.py              # Entry point for AI assistance API
│
├── settings/
│   ├── __init__.py
│   ├── app_settings.py          # Configuration settings (like region, API keys, etc.)
│   └── aws_config.py            # AWS configuration settings (keys, tokens)
│
├── requirements.txt             # Dependencies
├── main.py                      # FastAPI app entry point
└── README.md                    # Documentation

Installation
Prerequisites
Python 3.8 or later
AWS Bedrock access (ensure you have the required credentials)
Pip (Python package manager)
Clone the Repository
bash
Copy
Edit
git clone https://github.com/your-username/ai_assistance.git
cd ai_assistance
Install Dependencies
bash
Copy
Edit
pip install -r requirements.txt
Usage
Run the Application Locally
Set up AWS Credentials:

Add your AWS credentials to settings/aws_config.py:

python
Copy
Edit
AWS_ACCESS_KEY = 'your-access-key'
AWS_SECRET_KEY = 'your-secret-key'
AWS_SESSION_TOKEN = 'your-session-token'
AWS_REGION = 'your-region'
Start the FastAPI Application:

bash
Copy
Edit
uvicorn main:app --reload
The application will run on http://127.0.0.1:8000.

Access the API Documentation:

Swagger UI: http://127.0.0.1:8000/docs
ReDoc: http://127.0.0.1:8000/redoc
API Endpoints
1. Get Answer
Endpoint: POST /ai-assistance/answer
Request Body:
json
Copy
Edit
{
  "question": "What is the capital of France?"
}
Response:
json
Copy
Edit
{
  "answer": "The capital of France is Paris."
}
2. Get Hints
Endpoint: POST /ai-assistance/hints
Request Body:
json
Copy
Edit
{
  "question": "Kanchan has to dye 30 dresses, she has finished dyeing 20. What fraction of dresses has she finished?"
}
Response:
json
Copy
Edit
{
  "hints": "Here’s how you can solve this problem:\n\n- Kanchan needs to dye 30 dresses in total.\n- She has finished 20 dresses so far...\n"
}
3. Get Feedback
Endpoint: POST /ai-assistance/feedback
Request Body:
json
Copy
Edit
{
  "student_answer": "Paris is the capital of Germany."
}
Response:
json
Copy
Edit
{
  "feedback": "The student's answer is incorrect. Paris is the capital of France, not Germany."
}
Deployment
Deploy on AWS EC2
Create an EC2 Instance:

Choose an Ubuntu AMI and ensure port 8000 is open in the security group.
SSH into the Instance:

bash
Copy
Edit
ssh -i "your-key.pem" ubuntu@your-ec2-public-ip
Install Python and Pip:

bash
Copy
Edit
sudo apt update
sudo apt install python3-pip
Clone the Repository and Install Dependencies:

bash
Copy
Edit
git clone https://github.com/your-username/ai_assistance.git
cd ai_assistance
pip3 install -r requirements.txt
Run the FastAPI App:

bash
Copy
Edit
uvicorn main:app --host 0.0.0.0 --port 8000
Access the API: Visit http://your-ec2-public-ip:8000.

Testing
Use Postman or curl to test the endpoints.
Example curl command:
bash
Copy
Edit
curl -X POST "http://127.0.0.1:8000/ai-assistance/answer" \
-H "Content-Type: application/json" \
-d '{"question": "What is the capital of France?"}'
Contributing
Fork the repository.
Create a new feature branch:
bash
Copy
Edit
git checkout -b feature/your-feature-name
Commit your changes:
bash
Copy
Edit
git commit -m "Add your message here"
Push to the branch:
bash
Copy
Edit
git push origin feature/your-feature-name
Open a pull request.
License
This project is licensed under the MIT License. See the LICENSE file for details.

yaml
Copy
Edit

---

### Step 2: Add `requirements.txt`

Create a `requirements.txt` file in the root of your project:

```plaintext
fastapi
uvicorn
boto3
pydantic
Step 3: Push to GitHub
Initialize a Git Repository:

bash
Copy
Edit
git init
git add .
git commit -m "Initial commit"
Create a GitHub Repository: Go to GitHub and create a new repository (e.g., ai_assistance).

Add Remote and Push:

bash
Copy
Edit
git remote add origin https://github.com/your-username/ai_assistance.git
git branch -M main
git push -u origin main
Step 4: Share the Repository
Share the GitHub repository URL with your team for collaboration and integration.
