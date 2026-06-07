This project is a Python-based backend system developed using the FastAPI framework. It exposes multiple API endpoints designed for processing video data, and therefore requires FFmpeg to be installed and properly configured in the system path during execution.

By default, the service operates on 0.0.0.0:8080. A separate frontend has not been implemented for direct interaction; instead, the API is validated and tested through FastAPI’s built-in interactive interface available at /docs.

The system includes functionalities such as video frame sampling and resolution downscaling, which can be accessed and executed via the API documentation interface. In addition, OpenCV is used to enable video playback, which depends on a GUI-supported installation of opencv-python.

The backend is designed to handle and store intermediate video outputs in an internal variable-like structure. This allows subsequent processing stages to automatically reuse previously generated results when no new input file is provided.

Deployment (Docker Setup)

To run the project, the repository must first be cloned. A .env file should then be created in the root directory containing the Groq API key in the format:
GROQ_API_KEY=your_api_key_here

After that, the Docker image can be built using:
docker build -t project-backend-docker .

Once the build is complete, the container is launched with port mapping on 8080 using:
docker run -p 8080:8080 project-backend-docker

Execution Flow

Inside the application, users must navigate to the Demo section. The backend URL should be correctly configured in the frontend environment (default is localhost:8080).

For advanced functionality:

SMPLR-X mesh visualization requires executing the provided notebook (internet connection required) and pasting the generated temporary Gradio link into the demo interface.
Webcam-based input can be activated by switching to webcam mode and initiating playback if necessary.
Video files can be uploaded directly using the upload option.
Processing can be controlled using Start Streaming and Stop Streaming actions.
