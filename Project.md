## Tell Us About Your Project
>> We developed a Project named 'Online Car Service Station'  that aims to streamline the process of booking car services online.You won't have to wait around or call the repair shop. You can see when a mechanic is available and book an appointment that suits you. We made sure that website is user-friendly. You can quickly find what you need, like choosing a service for your car or picking a time for your appointment.The backend was built using Spring Boot, which provided a robust foundation for the API. On the frontend, we used React.js to create a user-friendly and responsive UI for customers and administrators.To enhance the state management and ensure a smooth flow of data within our frontend components, we decided to integrate Redux into our project.

## What is Your Role ?
>> Throughout our 'Online Car Service Station' project, I've been actively involved in both the frontend and backend development. My primary responsibility was working on the frontend using React.js, where I focused on creating a user-friendly and responsive interface. I've been responsible for designing and implementing the user interfaces, ensuring a smooth user experience.

Additionally, I've also made significant contributions to the backend using Spring Boot. I've been involved in tasks such as API integration, database design, and assisting in implementing certain backend features.

Working closely with my project partners, I've enjoyed the opportunity to work on a wide range of tasks, which has helped me learn more skills. I've had a flexible role that helps make sure the frontend and backend parts of our project work well together.

## How did you handle user authentication and authorization in your project ?
>> For user authentication, we implemented system that allows users to create accounts securely and log in. Here's how we handled it:
- Registration: Users, including customers and administrators, can create their accounts by providing necessary information such as username, password, and contact details. We ensured that this information is securely stored.
- Secure Password Storage: We used encryption techniques to securely store user passwords. Passwords are hashed before being stored in the database, making it extremely difficult for unauthorized individuals to access user credentials.
Token-Based Authentication: We adopted token-based authentication, using technologies like JSON Web Tokens (JWT). When users log in, they receive a unique token that verifies their identity for subsequent requests. This token is securely transmitted and stored on the client side.

>> Authorization is all about determining what actions different types of users can perform within the system. We implemented role-based access control to manage user permissions effectively:
- Roles: Users are assigned roles based on their type — customer or administrator. Each role has specific permissions and access rights.
- Access Control: Access to different parts of the application is controlled based on roles. For instance, customers can book appointments and leave reviews and administrators have full control over services, and system settings.