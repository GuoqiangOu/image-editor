# Image Editor
**Team Member:** Xiao Lei Zhang, Guoqiang Ou, YongTian Chen

### Description of this application:

An image editor application which allows gallery owners of the Web Gallery to edit their uploaded images by applying 2D and 3D effects. The 2D editor is similar to Microsoft Paint. The 3D editor is similar to Microsoft Paint 3D. The application also allows image processing using deep learning models from IBM Watson such as Neural Style Transfer API.

### The key features that will be completed by the Beta version:

Basic gallery functionalities (same as homework):

**Non-authenticated** users can:
- register or login to the application

**Authenticated** users can:
- access 2D/3D Editor
- view uploaded images in 2D or 3D editor mode

For 3D Editor features, **authenticated** user can:
- insert planes, 3D cubes, texts, other objects, and images into scene
- insert lighting effects
- scale, rotate, translate 3D objects using mouse or edit properties via side menu
- change color of inserted objects via side menu
- add adjustable fog effects via side menu
- save 2D images from 3D editor
- toogle object visibility via side menu
- change object name via side menu
- change scene background color via side menu
- display type of object and object geometry type on side menu
- create new 3D drawings (clears current scene)
- delete inserted objects using Del key
- move through scene using arrow keys

### Additional features that will be complete by the Final version:

For 3D Editor features:, **authenticated** user can:
- export or import models from 3D editor as json 
- logout or return to home page of website

For 2D Editor features, **authenticated** users can:
- insert text, lines, circles, shapes, images onto canvas
- select multiple objects by double clicking
- scale, rotate, or translate elements on the panel using mouse
- apply filters such as blur, grayscale, etc. to selected objects
- apply rotation and flip to selected objects
- toogle bold, underline, italics on inserted selected text
- inserted selected objects are removable using Del key
- selected text objects are also removable using delete textbox button
- change fill color of selected objects
- export canvas as png

For image processing features implemented with IMB Watson Vision Model Apis, 
**authenticated** user can:
-  image colorizer, image super resolution, image neural style transfer (Optional)

### The technologies will be used:
1. Frontend Framework: **Angular**
2. Backend Runtime Environment: **Node.js**
3. Backend Framework: **Express.js**
4. 2D image editing libarary: **snap.svg**
5. 3D image editing libarary: **three.js**
6. Machine Learning APIs: **IBM Watson** (Optional feature)

### The top 5 technical challenges:
1. Work with 3D: implement 3D image editor
2. Eliminating security issues
3. Learning numerous libraries/frameworks in a short period time
4. Implement editor functions involving mouse and keyboard events (e.g. resizing, dragging, moving through space)
5. Implement Frontend using AngularJS and integrating web applications (2D/3D Image Editors)

### Website
Visit at imageditor.me

### Demo Video
https://youtu.be/2YHazk0s778

## API Documenting

## Image Editor

## Project Assignment: API Documentation ##

1. Post
    - Description: Sign up the user by given username and password
    - Request: `POST /create/`
    * content-type: `application/json`
    * body: user object
        * username(string) the username need to sign up given by request
        * password(string) the password need to sign up given by request
        * firstname(string) the user firstname given to sign up by request
        * lastname(string) the user lastname given to sign up by request
    - Request 200
    * content-type: `application/json`
    * body: user object
        * username(string) the username given by request
        * hash(string) the randaom generated hash
        * firstname (string) the user firstname 
        * lastname (string) the user lastname
        * createDate (Date) Date that the use object been created
    - Respond: 400
        * username or password does not exist
    - Respond: 500
        * connection err
    - Respond: 409
        * Username already exist
    - curl example:
    `curl -H "Content-Type: application/json" -X POST -d '{"username":"alice","password":"alice"}' -c cookie.txt localhost:4000/create/`

2. Post
    - Description: Sign in the user by given username and password
    - Request: `POST /authenticate/`
    * content-type: `application/json`
    * body: user object
        * username(string) the username need to sign up given by request
        * password(string) the password need to sign up given by request
        * firstname(string) the user firstname given to sign up by request
        * lastname(string) the user lastname given to sign up by request
    - Request 200
    * content-type `application/json`
    * body: user object 
        * username(string) the username given by request
        * hash(string) the randaom generated hash
        * firstname (string) the user firstname 
        * lastname (string) the user lastname
        * createDate (Date) Date that the use object been created
    - Respond: 400
        * username or password does not exist
    - Respond: 500
        * connection err
    - Respond: 401
        * wrong password or username
    - curl example:
    `curl -H "Content-Type: application/json" -X POST -d '{"username":"alice","password":"alice"}' -c cookie.txt localhost:4000/authenticate/`

3. Get
    - Description: Get Use by input ID
    - Request: `GET /current/`
    - Request 200
    content-type: `application/json`
    * body: user object
        * id(int) the id create when the user object was created
    - curl example: 
    `curl -b cookie.txt -c cookie.txt localhost:3000/current/`

4. Put
    - Description: Update the use by input ID
    - Request: `GET /:id/`
    - Request 200
    content-type: `application/json`
    * body: user object
        * id(int) the id create when the user object was created
    - Respond: 409
        * Username already exist
    - curl example: 
    `curl -b cookie.txt -c cookie.txt localhost:3000/current/`



