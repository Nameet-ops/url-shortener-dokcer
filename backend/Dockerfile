#using an official lightweight python runtime 
FROM python:3.11-slim

# set the working directory in the container
WORKDIR /app

#copy the dependencies file and install them
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

#copy the rest of the app code 
COPY . .

#expose the port fastapi will run on
EXPOSE 8000

# command to run the app using Uvicorn
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]

