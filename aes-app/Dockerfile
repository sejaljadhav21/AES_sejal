FROM python:3.12.5

# Install Java if using language_tool_python
RUN apt-get update && apt-get install -y openjdk-17-jre

WORKDIR /app
COPY . /app

RUN pip install --upgrade pip
RUN pip install -r requirements.txt

ENV JAVA_HOME /usr/lib/jvm/java-17-openjdk-amd64/
ENV PATH $JAVA_HOME/bin:$PATH

# Start with gunicorn (or use python app.py for debug)
CMD gunicorn -b 0.0.0.0:$PORT app:app
