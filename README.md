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
