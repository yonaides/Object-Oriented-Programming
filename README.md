# What is object oriented programming?
Object-Oriented Programming is a way of writing code that allows you to create different objects from a common object. The common object is usually called a blueprint while the created objects are called instances.

Each instance has properties that are not shared with other instances. For example, if you have a Human blueprint, you can create human instances with different names.

Object-Oriented Programming is about structuring code when you have multiple levels of blueprints. This is commonly called Inheritance or subclassing.

# Why would you use it?
It's modularity for easier troubleshooting, Reuse of code through inheritance, Flexibility through polymorphism, Effective problem solving.

Since each object has the same type of properties, it would be better to have a template for the user objects that we just populate with data when we want to create a new user object

# In which cases would an OOP pattern be a better choice?
It `s better choice when you need to create an App with diferent module and need save data in relational database.

# The project that I will describe you is Foot History App.
#### **How would people use it?**
People use this app for shared food with family/ friends at holiday and others celebration days.

### **Describe the application flow from the user's point of view (user stories).**
- The user can create the acccount with some data, name, genre, age, email, password.
- Later can write a post with photo's specify the place.
- The photo can shared with others app.
- Upload your photo.
- You can follow other people and people can follow you.
- You can edit and delete post.
- You can cancel your personal account.

#### **What is the application's purpose, and how would people use it?**
The purpose of Foot History is create a album of foot'photo with friends and/or family,
the app show your post like a album show the date with some pretty format.

### **What information would they enter, and what would be received?**
**The information that your enter is:**
- Data of users like firstname, lastname, age, single/married, your family members, email, password.
- Upload photos, commets.

### **What would be received?**
 **The information that your received**
 - Notification when your friends upload comments.
 
### **Some user performs any kind of CRUD operation**
- Creation account Create/Edit/Read users data information.
- For creation posts of users Create/Edit/Delete.
- List of Following Create/Edit/Read.
- List of invitation Create/Edit/Read.
- List of Posts Create/Edit/Read/Delete.

### **Pseudocode**
```
 //List of main Objects
  User = {
     id: UUID, // clave unica
     firstname:'',
     lastname: '',
     email: '',
     confirm: true/false,
     birthday: Date,
     active: true/false,
 }
 
 Post = {
     id: UUID, // clave unica
     userId: Integer, // User Id Fk
     description: String,
     image: File,
     active: true/false
 }
 
 Invitation = {
     id: UUID, // clave unica
     userId: Integer, // user id Fk
     invitationUser: Integer, // users cant invitation
     accepted: true/false,
 }
 
 Following = {
     id: UUID, // clave unica
     userId: Integer, // user id Fk
     followingUser: Integer, // users cant following
     createdAt: Date
 }
 
 // Constructed Main Objects
 const User = {
     id: uuidv4(),
     firstname:'Yonaides',
     lastname: 'Tavares',
     email: 'yonaides@gmail.com',
     confirm: true,
     birthday: new Date('1981-10-01'),
     active: true
 }
 
 const post = {
     id: uuidv4(),
     userId: user.id,
     description: "christmas dinner table",
     image: [Blob], // image File
     active: true
 }

 const invitation = {
     id: uuidv4(), // clave unica
     userId: user.id, // find in object User
     invitationUser: user.id, // users cant invitation
     createdAt:  new Date ('2021-01-28'),
     accepted: true,
 }

 const following = {
     id: uuidv4(), // clave unica
     userId: user.id, // user id Fk
     followingUser: user.id, // users cant following
     createdAt: new Date ('2021-01-28')
 }

// How they would relate to each other. 
    Object [Post] contains the uuid of User Object
    Object [invitation] contains the uuid of User Object at userId and invitationUser
    Object [following] contains the uuid of User Object at userId and followingUser
   
```
