# **EventHiveUofT** 🎉

## **Authors and Contributors** 👥

- **Main Authors**:
    - **Naoroj Farhan**     [@pirate2580](https://github.com/pirate2580)
    - **Fiona Verzivolli**  [@FionaVerzivolli](https://github.com/FionaVerzivolli)
    - **Andrew Sasmito**    [@AndrewSasmito](https://github.com/AndrewSasmito)
    - **Edric N.H.G. Ho**          [@Edric.main(cryingFace)](https://github.com/Edric-Ho)

- **Special Thanks**: Collaborators at the University of Toronto, including project mentors, peer reviewers, and support from the teaching team.

The main contributors will actively update the application to enhance its features, fix bugs, and ensure the user experience is as smooth as possible. Additional contributions are always welcome!!!

## **Summary** 📝

**EventHiveUofT** is a centralized event management system specifically tailored for students and staff at the [**University of Toronto**](https://www.utoronto.ca). It is designed to streamline the process of organizing, discovering, and participating in campus events by offering an integrated platform that is accessible, easy-to-use, and informative.

This project solves the challenge of fragmented event information by providing a **comprehensive solution** that includes an **interactive campus map**, **event creation and management**, **real-time RSVP**, **email notifications**, and **user accessibility features**. Accessibility features are a primary concern, making sure that everyone can fully engage with the university's vibrant campus life.


**EventHiveUofT** aims to build a **connected campus community** where students and staff can easily find opportunities to network, learn, and socialize through organized events. 🚀

## **Table of Contents** 📑

1. [Features](Features)
2. [Installation](installation)
3. [Usage](usage)
4. [License](license)
5. [Feedback](feedback)
6. [Contribution](contribution)
7. [Maintenance](maintenance)
8. [FAQs and Troubleshooting](faqs-and-troubleshooting)
9. [Future Features](future-features)

## **Features** 🚀

### **1. Event Creation and Management** ✏️

Users can **create**, **modify**, and **delete** events on campus using an intuitive form. The following details can be added to an event:

- **Event Name**
- **Event Organizer**
- **Date and Time**
- **Location** (by latitude(43 to 44) and longitude(-78 to -79))
- **Event Description**
- **Event Type(Tag)**

#### **Technical Implementation**

- The `CreateEventInteractor` and `ModifyEventInteractor` classes are the core drivers of the event management feature. These classes handle **data validation**, **data storage**, and **event modification**.
- Events are stored using `FirebaseService` for reliability, ensuring data is always available in real-time.

#### **Screenshots**

- **Event Creation Page**:
     <img width="1512" alt="Filled_create_event_page" src="https://github.com/user-attachments/assets/38c22cdc-7b3c-4f0d-9b61-43280bd36b72">


### **2. Interactive Campus Map** 🗺️

The application features an interactive map of the **University of Toronto campus** where users can visually explore:

- **Event Locations**
- **Building Information** (e.g., Robarts Library, Sidney Smith)

#### **Technical Implementation**

- The map uses the `JXMapViewer` library to provide smooth navigation across different campus buildings.
- Events are marked with **pins** that users can **hover over** or **click** to get more information.
- The `ViewEventInteractor` and `ViewRSVPInteractor` manage all user interactions with the map, ensuring the events are displayed accurately.

#### **Screenshots**

- **Interactive Map**:

<img width="1512" alt="markers_on_maps" src="https://github.com/user-attachments/assets/17d79ac1-1411-455e-9e2c-7e306f786533">


### **3. RSVP Functionality** 📅

Users can **RSVP** to events, which allows them to keep track of their plans. This also enables organizers to see attendees and send out **notifications** to those registered.

- Users can also **view the list of events** they have RSVP’d to, making it easy to manage their schedule.

#### **Technical Implementation**

- The `RSVPEventInteractor` processes the RSVP requests and ensures that users are properly added to the list of attendees.
- The `RSVPEventUserDataAccessInterface` provides methods for managing RSVP details within Firebase.

#### **Screenshots**

- **RSVP Screen**:
  
 <img width="727" alt="EventDescription" src="https://github.com/user-attachments/assets/88ca823f-7055-4ff0-b983-30779d6358b4">

### **4. User Registration and Login System** 🔐

To enhance security and personalization, **users must register** with their email and a password to access the platform. This ensures:

- **Data privacy** and personalized experiences.
- **User accounts** that can be managed independently.

#### **Technical Implementation**

- The `RegisterInteractor` and `LoginInteractor` classes handle the registration and login processes, using the Firebase Authentication SDK.
- The **registration form** is protected with validation checks for **duplicate usernames**, **proper email formatting**, and **password strength**.

#### **Screenshots**

- **Registration Page**:

<img width="801" alt="Registration_view" src="https://github.com/user-attachments/assets/bd86819f-3eaf-466f-a91a-12d61b34c045">


### **5. Email Notifications** 📧

Users and event organizers are kept informed through **email notifications**. These are triggered for events like:

- **RSVP Confirmations**
- **Event Reminders**

#### **Technical Implementation**

- The `NotifyUserInteractor` collaborates with the `EmailSender` and `FirebaseService` classes to manage email notifications.
- Emails are **customizable** by organizers and ensure all users remain informed about their event commitments.

#### **Screenshots**

- **Notify RSVPed User**:

<img width="1512" alt="Notification" src="https://github.com/user-attachments/assets/8c91a812-74f0-4c08-b942-e910e8600609">


### **6. Accessibility Features** ♿

In accordance with **Universal Design Principles**, the app includes:

- **Adjustable Zoom Levels** for users with **visual impairments**.
- **Color-blind Friendly Markers** on the map to ensure inclusivity.
- Planned future enhancements include a **screen reader** for visually impaired users.

#### **Technical Implementation**

- The `DisplayEventPresenter` ensures that all displayed content is **clear**, **legible**, and **easy to navigate**.

### **7. View Created Events** 👀

Event organizers can **view all the events** they have created for easier management and modifications.

- The feature provides a **summary view** of the events created, including **date**, **time**, and **RSVP details**.

#### **Technical Implementation**

- The `ViewCreatedInteractor` uses the `ViewCreatedDataAccessInterface` to retrieve and present all created events.
- The **presenter** formats the data for easy viewing within the user interface.

#### **Screenshots**

- **View Created Events**:

<img width="1512" alt="Create_event_view" src="https://github.com/user-attachments/assets/1b356f2e-41d6-4af8-b423-1d6fed772951">


### **8. Modify User Details** ✏️

Users can easily modify their **account details**, such as changing their **email** or **password**.

#### **Technical Implementation**

- The `ModifyUserInteractor` manages the user details update process.
- The `ModifyUserDataAccessInterface` ensures that changes are securely updated in Firebase.

## **Installation** 🛠️

To get started with **EventHiveUofT**, follow these detailed steps:

1. **Clone the Repository** 📂:

   ```sh
   git clone https://github.com/FionaVerzivolli/EventHiveUofT.git
   cd EventHiveUofT
   ```

2. **Java Installation** ☕:

    - Ensure **Java 11** is installed. It is recommended to use [AdoptOpenJDK](https://adoptopenjdk.net/).
    - Verify installation:
      ```sh
      java -version
      ```

3. **Maven Installation** 📦:

    - Install **Maven** (minimum version 3.6.0).
    - Follow the [Maven Installation Guide](https://maven.apache.org/install.html).
    - Verify Maven installation:
      ```sh
      mvn -v
      ```

4. **Firebase Setup** 🔧:

    - Set up Firebase by obtaining the `firebase-service-account.json` from the Firebase console.
    - **Steps to Obtain JSON**:
        1. Visit the **Firebase Console**.
        2. Navigate to **Settings > Service Accounts**.
        3. Click **Generate New Private Key** and save it in the project under `/private/`.

   ![ServiceAccount.Json](https://s3.amazonaws.com/cdn.freshdesk.com/data/helpdesk/attachments/production/72045913053/original/wtqtJOcKiKJ2C89JLmjFYvukuQOyHfGVwg.png?1681913930)

5. **Environment Variables** 🌐:

    - Add an environment variable for the Firebase service account file path:
      ```sh
      export GOOGLE_APPLICATION_CREDENTIALS="/path/to/firebase-service-account.json"
      ```

6. **Build and Run the Project** 🚀:

    - **Build** the project using Maven:
      ```sh
      mvn clean install
      ```
    - **Run** the project:
      ```sh
      mvn spring-boot:run
      ```

7. **Dependencies**:

    - The dependencies include:
        - **Spring Boot Starter** for the backend framework.
        - **Firebase Admin SDK** for user management and notifications.
        - **JXMapViewer** for the interactive campus map.
        - All dependencies are listed in `pom.xml` with required versions.

**Common Issues** ⚠️:

- **Firebase Connection Issues**:
    - Double-check the path to `firebase-service-account.json`.
    - Ensure the credentials have sufficient permissions.
- **Maven Build Errors**:
    - Clean the cache and retry:
      ```sh
      mvn clean install
      ```
- **Port Conflict**:
    - Make sure the default port (**8080**) is free or modify it in `application.properties`.

## **Usage** 💻

### **1. Registration and Login** 🔐

- **Register** with your email and password.
- **Login** to access features.

### **2. Create and Manage Events** ✏️

- Navigate to the **Event Creation Page**.
- Fill out the **event form** and click **Submit**.
- To **edit an event**, go to **Your Events** and click **Edit**.

### **3. Interact with the Campus Map** 🗺️

- **Explore Events** across the campus.
- **Hover** or **click** on markers to see details.

### **4. RSVP and Notification** 📅

- Click **RSVP** to confirm attendance.
- **Receive notifications** for updates and reminders.

## **License** 📜

This project is licensed under the **MIT License**, which allows for free use, modification, and distribution of the code with proper attribution. For more details about your rights and limitations under this license, see the `LICENSE` file included in this repository.

### **Summary of the License**:

- **Permitted**: Modification,and private use.
- **Conditions**: The code must include attribution to the original authors.
- **Limitations**: There is no warranty, and the contributors are not liable for any damages.

## **Feedback** 💬

We value your feedback to continuously improve **EventHiveUofT**. If you have suggestions, encounter issues, or simply want to provide us with some comments, please use the methods below:

1. **GitHub Issues**:

    - Report bugs or request features directly through our [GitHub Issue Tracker](https://github.com/FionaVerzivolli/EventHiveUofT/issues). Use clear titles and descriptions to help us understand the issue.

2. **Google Form**:

    - Fill out our [Feedback Form](https://docs.google.com/forms/d/e/1FAIpQLSe0zIZ00Kl7o03l7Zc02Nt0jrG6-B35kbchZ-QnLT_0drhsyQ/viewform?usp=pp_url) to share your thoughts, experiences, or suggestions.

**Guidelines for Feedback**:

- **Be Specific**: Describe issues or suggestions clearly, including screenshots if possible.
- **Constructive Language**: Please use respectful and helpful language to foster productive discussions.
- **Response Time**: We aim to respond to feedback **ASAP**.


## **Contribution** 🤝

Contributions are welcome and encouraged! Here’s how you can get involved:

### **How to Contribute**:

1. **Fork the Repository**:

    - Click the **Fork** button at the top of the repository page.
    - This creates a copy of the repository under your GitHub account.

2. **Clone the Fork**:

   ```sh
   git clone https://github.com/FionaVerzivolli/EventHiveUofT.git
   cd EventHiveUofT
   ```

3. **Create a Branch**:

    - Use a descriptive name for your branch:
      ```sh
      git checkout -b new-feature-branch
      ```

4. **Make Changes and Commit**:

    - Implement your changes, ensuring the code is well-documented.
    - Run all tests before committing to make sure nothing is broken.
    - Commit changes:
      ```sh
      git add .
      git commit -m "Add new feature: <description>"
      ```

5. **Push to GitHub**:

   ```sh
   git push origin new-feature-branch
   ```

6. **Create a Pull Request**:

    - Navigate to the original repository and click **New Pull Request**.
    - Fill out the description clearly detailing the changes made.

### **Contribution Guidelines**:

- **Code Style**: Follow our Java coding standards. This helps maintain readability across the entire project.
- **Tests**: Ensure unit tests are added for new features, and all existing tests pass.
- **Documentation**: Update the README and any other relevant documentation to reflect changes.
- **Pull Request Reviews**: Wait for project maintainers to review your changes. Feedback might be provided to make modifications before merging.

**Please read the following PR guideline provided by GitHub**:

- [Best practices for pull requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/getting-started/best-practices-for-pull-requests)


### **Development Tips**:

- Use **IntelliJ IDEA** for development and set up **Google Checkstyle** for consistent code quality.
- **Run tests** regularly using:
  ```sh
  mvn test
  ```

## **Maintenance** 🛠️

### **Current Maintenance Plan**:

- **Weekly Updates**: The main contributors will push updates and bug fixes on a regular basis to ensure stability and improvements.
- **Dependency Updates**: All dependencies listed in the `pom.xml` will be reviewed and updated if needed.
- **New Feature Releases**: Major new features will be developed on a separate branch and merged after thorough testing, following the **semantic versioning** guidelines.

**Monitoring Tools**:

- **GitHub Actions**: Automated builds and tests will be used to maintain code quality.
- **Firebase Dashboard**: To monitor real-time data and ensure stability in user authentication and data management.

**Future Maintenance Considerations**:

- **Adding Support for New Features**: Plans to implement user-customizable UI themes to ensure **inclusive usage** by using React.
- **Scaling Application**: If user adoption grows significantly, migrate to a more scalable database and consider incorporating **cloud computing solutions** like **AWS Lambda** for event processing.




## **FAQs and Troubleshooting** 🛠️


### **FAQs**:


**Q: What should I do if I encounter an error during the registration process?**

- **A**: Ensure all form fields are correctly filled out (username, email, password). Check if the email format is valid and the username isn't already taken.


**Q: Why am I unable to see all events on the map?**  

- **A**: Ensure that you have **enabled all event filters**. By default, only certain types of events may be displayed based on your preferences. Check the filters on the sidebar and adjust the event filter.


**Q: Can I delete an event after I have created it?**  

- **A**: Yes, you can delete an event that you’ve created. Go to **Modify Event**, select the **Delete Event** at the bottom, and click on it. 


**Q: Why am I not receiving email notifications?**  

- **A**: Check your email settings to ensure notifications are not being blocked. Additionally:
  - 1. Verify that your **email address** is correct in **Profile Settings**.
  - 2. Check your **spam folder**.


**Q: How do I update event information after it’s been created?**  

- **A**: If you are the event organizer, navigate to **Your Events** from the main menu. Click on **Modify Event** next to the event you wish to modify, make the necessary changes, and save them. The attendees will be notified of any updates automatically.



**Q: Can I use EventHiveUofT if I’m not affiliated with UofT?**  

- **A**: The platform is primarily built for the **University of Toronto** community, but non-affiliated users can still join **public events** if allowed by the event organizer. Please note that some features, like **creating events**, may be restricted to authenticated UofT users.


**Q: Why can't I find certain buildings on the interactive map?**  

- **A**: Ensure that the map is **fully loaded** and that you are zoomed in enough. Some smaller buildings or less significant landmarks may not be visible at a higher zoom level. The list of buildings includes major UofT locations such as **Robarts Library**, **Sidney Smith Hall**, and more.



### **Common Issues and Troubleshooting:**

**Issue: Firebase Connection Fails**

**Solution**:

- **Verify Service Account Path**: Ensure the `firebase-service-account.json` is correctly placed in the `/private/` directory and that its path matches the **GOOGLE_APPLICATION_CREDENTIALS** environment variable.
- **Permission Checks**: Confirm that the credentials have the required permissions within the Firebase project to access **Firestore**, **Authentication**, and other used services.
- **Network Issues**: If you're behind a firewall or VPN, check that the required ports for Firebase are not blocked.

<img width="250" alt="Screenshot 2024-12-03 at 22 52 37" src="https://github.com/user-attachments/assets/5c3f6164-2321-45ac-9015-32414d00f60f">


---

**Issue: Maven Build Errors**

**Solution**:

- **Run Clean Build**: Clear previous build artifacts by running:
  ```sh
  mvn clean install
  ```
- **Update Dependencies**: Ensure that all dependency versions are compatible with each other by checking the `pom.xml` file.
- **JDK Issues**: Make sure you are using **Java 11** or higher, and that the Java environment variable (`JAVA_HOME`) points to the correct version.

---

**Issue: Map Pins Not Showing Up**

**Solution**:

- **Dependencies Set Up**: Verify that the project dependencies have been setted up and Maven has built the porject successfully.
- **Map Data Not Loaded**: Check the console logs for errors related to loading the **JXMapViewer** data. Make sure the data endpoints are properly connected.

<img width="1512" alt="markers_on_maps" src="https://github.com/user-attachments/assets/4db8d14f-9d14-4a3a-bfd1-c6e9051c9d66">

---

**Issue: Unable to RSVP to Events**

**Solution**:

- **Login Check**: Make sure you are logged in before attempting to RSVP to an event.
- **Event Capacity**: Verify that the event isn’t at full capacity. The RSVP function will not allow users to join if the event has reached its limit.
- **Network Stability**: Ensure your network connection is stable, as RSVP actions require an active connection to Firebase.

<img width="1512" alt="RSVP_success_view" src="https://github.com/user-attachments/assets/6abf6d54-c3ed-4a34-b9a8-15d517a27a42">


## **Future Features** 🚀

- **Mobile App Integration** 📱: Build an Android and iOS version of **EventHiveUofT** to extend accessibility and allow users to RSVP to events on-the-go.
- **Personalized Recommendations** 💡: Use AI-based algorithms to recommend events to users based on their interests and past activity.
- **Screen Reader Compatibility** 🔊: Integrate screen reader support to make the application more accessible to users with visual impairments.
- **User-Defined Event Categories** 📂: Allow users to create custom event categories to better organize and filter the events they are interested in.
- **Push Notifications** 🔔: Include push notifications for important event updates, RSVP reminders, and upcoming deadlines.


## **Contact Information** 📧

For any additional inquiries or support, feel free to contact us via the following channels:

- **Email**: ________________________________

Thank you for using **EventHiveUofT**! We are excited to have you join our vibrant community and help you discover amazing events on campus. 🙌
