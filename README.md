# ASL integrated 🤖 Generative AI 🎥 for YouTube 🌐💬 with Google Cloud

## Project Overview:

This project aims to create an integrated solution leveraging Google Cloud services to generate ASL (American Sign Language) interpreted videos for YouTube content. The solution includes three main components: a mobile application, a PC application, and a frontend web interface, each encapsulated in a Docker container for easy deployment and scalability.

## Technologies Used:
* Google Cloud Run: For deploying and managing containerized applications.
* Google App Engine: For scalable web application hosting.
* Google Compute Engine: For customizable virtual machine instances.
* Docker: For containerization of applications.
* Google Container Registry: For storing and managing Docker container images.
* Google Speech-to-Text API: For converting speech into text.
* Google Cloud Storage (Cloud Bucket): For storing and managing data objects.
* Google Vertex AI: For building and deploying machine learning models.
* Generative Language API: For generating text-based content using machine learning models.
* Streamlit: For building interactive web applications.
* Matplotlib: For creating visualizations.
* Pillow (PIL): For image processing.
* NumPy: For numerical operations.
* re: For regular expression operations.
* Gradio: For building interactive web applications.

## File Structure:

- **Finale.zip**: Contains Dockerfile and necessary project files for the mobile application.
- **Finale_PC.zip**: Contains Dockerfile and necessary project files for the PC application.
- **Finale_Frontend.zip**: Contains Dockerfile and necessary project files for the frontend web interface.

## Deployment Command:

To deploy the Docker containers to Google Cloud Run, follow these steps:

1. Deploy the PC application:

```bash
gcloud builds submit --tag gcr.io/<PROJECT_ID>/finale-pc --dir /path/to/Finale_PC.zip --timeout=2h

gcloud run deploy --image gcr.io/<PROJECT_ID>/finale-pc --platform managed --region REGION --allow-unauthenticated
```

2. Deploy the mobile application:
```bash
gcloud builds submit --tag gcr.io/<PROJECT_ID>/finale-mobile --dir /path/to/Finale.zip --timeout=2h

gcloud run deploy --image gcr.io/<PROJECT_ID>/finale-mobile --platform managed --region REGION --allow-unauthenticated

```

Replace <PROJECT_ID> with your Google Cloud project ID and REGION with the appropriate region where you want to deploy your services.

3. After deploying both applications, obtain their respective URLs.
4. Update the frontend web interface to use these URLs for redirection.
5. Once updated, containerize the frontend application:

```bash
gcloud builds submit --tag gcr.io/<PROJECT_ID>/finale-frontend --dir /path/to/Finale_Frontend.zip --timeout=2h

gcloud run deploy --image gcr.io/<PROJECT_ID>/finale-frontend --platform managed --region REGION --allow-unauthenticated

```
Replace REGION with the appropriate region where you want to deploy your frontend.

## Made with &hearts; by TY_25
