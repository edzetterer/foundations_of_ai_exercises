FROM python:3.11-slim

LABEL maintainer="University of Bremen – Institute for Artificial Intelligence"
LABEL description="FAI SS2025 – Search Algorithms Exercises"

WORKDIR /home/jovyan/work

# Install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy notebook and exercise files
COPY notebooks/ ./notebooks/

EXPOSE 8888

CMD ["jupyter", "lab", \
     "--ip=0.0.0.0", \
     "--port=8888", \
     "--no-browser", \
     "--NotebookApp.token=''", \
     "--NotebookApp.password=''", \
     "--notebook-dir=/home/jovyan/work"]
