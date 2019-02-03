FROM python:3
ENV PYTHONUNBUFFERED 1
ENV SECRET_KEY SECRET_KEY
# Set the application directory
WORKDIR /code
# Install our requirements.txt
# RUN apk add build-base
# RUN apk add postgresql-dev
ADD requirements.txt /code/requirements.txt
RUN pip install -r requirements.txt 
# RUN pip install --upgrade setuptools \
    # && pip install ez_setup \
    # && python -m venv venv \
    # && source venv/bin/activate \
    # && pip install -r requirements.txt 
# RUN export SECRET_KEY=SECRET_KEY
# Copy our code from the current folder to /code inside the container
ADD templates/ /code/templates
ADD blockchain/ /code/blockchain
ADD manage.py /code
ADD static/ /code/static
ADD explorer/ /code/explorer
ADD grinexplorer/ /code/grinexplorer
EXPOSE 80
# Define our command to be run when launching the container
CMD ["python", "manage.py", "migrate"]
CMD ["python", "manage.py", "runserver", "0.0.0.0:80"]



