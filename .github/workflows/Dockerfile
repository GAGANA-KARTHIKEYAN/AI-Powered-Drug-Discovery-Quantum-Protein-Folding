FROM python:3.9-slim

WORKDIR /app

# Install system dependencies (required for matplotlib and RDKit)
RUN apt-get update && apt-get install -y \
    libx11-6 \
    libxext6 \
    libxrender1 \
    libfontconfig1 \
    && rm -rf /var/lib/apt/lists/*

# Install Python packages
RUN pip install --no-cache-dir \
    streamlit \
    pandas \
    numpy \
    matplotlib \
    seaborn \
    scikit-learn \
    tensorflow \
    torch \
    pennylane \
    rdkit-pypi

# Copy application files
COPY . .

# Expose Streamlit port
EXPOSE 8501

# Run the Streamlit app
CMD ["streamlit", "run", "app.py", "--server.port=8501", "--server.address=0.0.0.0"]
