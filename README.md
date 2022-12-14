
# Workshop: Avatar Upload - Fullstack

Demo: [https://avatar-upload-ui.vercel.app](https://avatar-upload-ui.vercel.app)

## General guidelines

Create an React App with a Signup page

Provide username, email, password and an avatar image

Allow picking a file using the input type "file"

Limit the file choice to images only!

Convert the picked image to a base64 encoded string, before sending it to the API

OnSubmit: Send data, including the encoded image, to the API
  - The API will forward the image to cloudinary and store the returned URL (!) in the database
  - Do NOT upload images directly from the frontend to Cloudinary, please :)


Create an API with a signup POST route.

In the API we wanna store a user object like this:
```
{
  "username": <String>,
  "email": <String>,
  "password": <String>,
  "imageUrl": <String> // e.g. "myFileUrl.cloudinary.com"
}
```

You do not need to hash passwords in the backend for now. Let's focus on the file part first :)

Use Cloudinary as file provider: 

- Cloudinary Signup: https://cloudinary.com/users/register/free
- Cloudinary Free Plan & Pricing: https://cloudinary.com/pricing (25 GB for free)


## Research topics

### Frontend

- How to work with the input "file" in React `<input type="file" onChange={...} />`
- Base64 image encoding. Test it out here: [https://www.base64-image.de](https://www.base64-image.de)
- How to convert an image chosen from a file input field into a base64 string using JavaScript (research "FileReader" class)
- How to assign a base64 encoded image to an `<img>` tag, for showing a preview

### Backend

- How to make a connection to cloudinary from the API
- Use the cloudinary package: https://www.npmjs.com/package/cloudinary
- Place the "Cloudinary connection string" in an .env file (you can find it in your Cloudinary dashboard)
- How to expand the JSON upload limit of express from 100 KB to 1 MB
- How to upload a base64 image string to Cloudinary using the Cloudinary node package
  - Checkout a sample here: [https://support.cloudinary.com/hc/en-us/community/posts/360009192212-Uploading-image-from-a-base64-string](https://support.cloudinary.com/hc/en-us/community/posts/360009192212-Uploading-image-from-a-base64-string)
- How to retrieve the URL to the uploaded file from Cloudinary
- Store the data and the avatar url in a "users" collection in your database
- Prefer the https URL for storage


## Resources

In case you get stuck on the way, look up the more detailed guide below or ask some teacher around ;)

https://github.com/losrobbos/file-upload-guide

