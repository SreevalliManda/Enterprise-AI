uv python pin 3.11.8
uv venv --python 3.11.8
source .venv/Scripts/activate
uv pip install langchain==0.3.27 langgraph==0.6.7 langchain-openai==0.3.33 python-dotenv==1.1.1
python -c "import importlib.metadata; print(importlib.metadata.version('langgraph'))"
uv pip install ipykernel jupyter