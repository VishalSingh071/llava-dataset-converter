LLaVA-Instruct-150K First Row Converter

Purpose: Processes the first row of the LLaVA-Instruct-150K dataset, converts it to JSON with user/agent conversation turns and image URLs, and saves to output_row1.json.

Prerequisites

Python 3.8+
Internet connection for dataset download
Optional: Hugging Face account for authentication

Installation

Install Python: python.org
Create virtual environment:python -m venv venv
source venv/bin/activate  # Linux/macOS
venv\Scripts\activate  # Windows


Install dependencies:pip install pandas datasets



Usage

Save convert_row1.py to project directory
Navigate to directory:cd path/to/project


Run script:python convert_row1.py


Output: output_row1.json in same directory

Configuration

Modify config in convert_row1.py for dataset schema:config = {
    "dataset_id": "llava_instruct_150k",
    "conversation_column": "conversations",
    "image_column": "image",
    "role_key": "from",
    "content_key": "value",
    "embed_image": True
}


For local files, set local_path (e.g., "data.json")

Troubleshooting

KeyError: Verify dataset schema:from datasets import load_dataset
dataset = load_dataset("liuhaotian/LLaVA-Instruct-150K", split="train", streaming=True)
print(next(iter(dataset)))


Dataset not loading: Check internet or use local file
Image URLs incorrect: Update URL base in script
Module errors: Reinstall dependencies:pip install pandas datasets



License

MIT License

