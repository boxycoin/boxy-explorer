FROM python:3
ENV PYTHONUNBUFFERED 1
ENV SECRET_KEY SECRET_KEY
# Set the application directory
RUN mkdir /code
WORKDIR /code
COPY requirements.txt .
RUN pip install -r requirements.txt 
# Copy our code from the current folder to /code inside the container
COPY . .
EXPOSE 8000
# Define our command to be run when launching the container
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]



