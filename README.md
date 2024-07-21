# Node.js File Upload Server with Express and Cloudinary

This is a simple Node.js server application that allows users to upload images and videos to the server. The application uses Express and the Express File Uploader middleware to handle file uploads. The uploaded files are then stored on Cloudinary, a cloud-based image and video management service. After a successful upload, the application sends an email to the user who uploaded the file, containing a link to the uploaded file.

## Getting Started

To get started with this application, follow these steps:

1. Clone the repository to your local machine.
2. Install the required dependencies using `npm install`.
3. Set up the environment variables for Cloudinary and your email service. You can do this by creating a `.env` file in the root directory of the project and adding the following variables:
```makefile
CLOUDINARY_CLOUD_NAME=<your cloudinary cloud name>
CLOUDINARY_API_KEY=<your cloudinary api key>
CLOUDINARY_API_SECRET=<your cloudinary api secret>
EMAIL_SERVICE_USER=<your email service user>
EMAIL_SERVICE_PASSWORD=<your email service password>
```
4. Start the server using `npm start`.

## File Structure

The application consists of four main files:

1. `index.js`: This file sets up the Express app, connects to the database and Cloudinary, and defines the endpoints for file upload.
2. `routes/FileUpload.js`: This file defines the routes for file upload, which include `imageUpload`, `videoUpload`, and `imageSizeReducer`.
3. `models/File.js`: This file defines the schema for the uploaded files and defines a post-save hook that sends an email to the user who uploaded the file.
4. `controllers/fileUpload.js`: This file contains the logic for handling file uploads, including checking file types, uploading to Cloudinary, and saving the file to the database.

## Endpoints

The application provides the following endpoints for file upload:

1. `POST /api/image-upload`: This endpoint handles image uploads. It accepts a `file` parameter containing the image to be uploaded.
2. `POST /api/video-upload`: This endpoint handles video uploads. It accepts a `file` parameter containing the video to be uploaded.
3. `POST /api/image-size-reducer`: This endpoint handles image size reduction. It accepts a `file` parameter containing the image to be resized and a `width` parameter specifying the desired width of the output image.

## Dependencies

This application uses the following dependencies:

1. `express`: A web framework for Node.js.
2. `express-fileupload`: A middleware for handling file uploads in Express.
3. `cloudinary`: A Node.js library for the Cloudinary API.
4. `mongoose`: A MongoDB object modeling tool for Node.js.
5. `nodemailer`: A module for sending emails from Node.js.
6. `dotenv`: A module for loading environment variables from a `.env` file.


#### Created by Adarsh Mishra