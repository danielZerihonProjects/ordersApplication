# Use the official Ubuntu 20.04 base image
FROM ubuntu:20.04

# Set the working directory in the container
WORKDIR /app

# Update package lists and install necessary dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-pip

# Copy the app.py and index.html files into the container
COPY app.py .
COPY index.html .

# Install Flask
RUN pip3 install Flask

# Run the Flask app
CMD ["python3", "app.py"]

