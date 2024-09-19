# Use the official Python image from the Docker Hub (version 3.9)
FROM python:3.9

# Set the working directory inside the container to /app
WORKDIR /app

# Copy the requirements.txt file into the container at /app
COPY requirements.txt .

# Install the required Python packages listed in requirements.txt, using --no-cache-dir to avoid caching the downloaded packages
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code from the local app directory to the /app directory in the container
COPY app/ .

# Expose port 80 to make the service accessible from outside the container
EXPOSE 81

# Run the application using Uvicorn, setting the host to 0.0.0.0 (to allow external connections) and the port to 80
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "81"]
