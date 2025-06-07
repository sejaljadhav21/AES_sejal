FROM python:3.12.5

# Install Java (OpenJDK 17)
RUN apt-get update && apt-get install -y openjdk-17-jre

WORKDIR /app

COPY . .

RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# Set JAVA_HOME (for language_tool_python)
ENV JAVA_HOME /usr/lib/jvm/java-17-openjdk-amd64/
ENV PATH $JAVA_HOME/bin:$PATH

CMD ["gunicorn", "app:app"]