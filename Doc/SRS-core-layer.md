# 1. Introduction

## 1.1 Purpose
This document outlines the specific requirements for the Core-Layer of MainOp, a Computerized Maintenance Management System (CMMS). It is designed to automate maintenance processes, minimize operational interactions, and integrate seamlessly with various environments. The Core-Layer serves as the foundation for system interactions, configuration, and data management.

## 1.2 Document Conventions
- **API**: Application Programming Interface - a set of routines, protocols, and tools for building software and applications.
- **GUI**: Graphical User Interface - a visual way of interacting with a computer using items such as windows, icons, and menus.
- **CLI**: Command Line Interface - a text-based interface used to operate software and devices.

## 1.3 Intended Audience and Reading Suggestions
This SRS is intended for software developers, system integrators, project managers, and technical stakeholders involved in the development and deployment of MainOp. It is recommended to start with the Product Scope for an overview, followed by detailed sections for in-depth understanding.

## 1.4 Product Scope
MainOp's Core-Layer is responsible for the primary operations essential to the system's functionality. It includes handling initial user-system interactions, managing configurations through APIs, executing database operations, and ensuring reliable communication between MainOp and external systems. This layer sets the foundation for the subsequent Integration-Layer and Application-Layer, ensuring a cohesive and efficient CMMS.

## 1.5 References
- MainOp Vision Document: A high-level document outlining the overall vision and objectives of the MainOp system.
- API Documentation Standards: Guidelines and protocols for developing and maintaining API documentation.

# 2. Overall Description

## 2.1 Product Perspective
The Core-Layer is an integral component of MainOp, designed to function as the backbone of the system. It interfaces directly with the underlying hardware and software infrastructure, providing a robust foundation for the Integration-Layer and Application-Layer. This layer is essential for ensuring the system's scalability, reliability, and ease of integration with various environments, including cloud platforms and on-premise servers.

## 2.2 Product Features
- **Admin-Listener**: Manages initial setup and user interaction, providing logs and system status updates.
- **Configuration Management**: Facilitates system configuration through API calls, allowing dynamic setup and modification.
- **Database Interactions**: Supports SQL queries for data manipulation and management, interfacing with various database systems.
- **API Integration**: Offers RESTful APIs for external system integration, ensuring seamless communication and interoperability.

## 2.3 User Classes and Characteristics
- **System Administrators**: Responsible for system setup, configuration, and maintenance. They require tools for efficient system management and monitoring.
- **Developers and Integrators**: Use the system's APIs for integration with other software and services. They need clear, well-documented APIs and robust tools for testing and deployment.

## 2.4 Operating Environment
The Core-Layer is designed to be environment-agnostic, capable of operating on various platforms including Windows, Linux, and MacOS for local setups, as well as cloud environments like AWS, Azure, and Google Cloud Platform. It should be efficient in both containerized and virtualized environments.

## 2.5 Design and Implementation Constraints
- The system must be implemented in programming languages that are platform-independent, such as Java or Python.
- The APIs must conform to RESTful standards and support JSON and XML data formats.
- Integration with various database systems should be supported, including MySQL, PostgreSQL, and Oracle.
- Security measures, including encryption and authentication, are mandatory to protect sensitive data and system integrity.

# 3. System Features

## 3.1 Admin-Listener

### 3.1.1 Description and Priority
The Admin-Listener is a critical component of the Core-Layer, responsible for managing initial interactions with the system. It has a high priority as it serves as the first point of contact for users and administrators, facilitating system setup and monitoring.

### 3.1.2 Stimulus/Response Sequences
- On system start-up, the Admin-Listener initializes and begins logging activities.
- It listens on configured ports and displays system status and available commands.
- When a user requests help or information, it provides relevant guidance and logs the interaction.

### 3.1.3 Functional Requirements
- FR1.1: Must initiate automatically upon system start-up and log its status.
- FR1.2: Should display system status and IP/port information for user interaction.
- FR1.3: Must respond to help requests with detailed API usage instructions and system information.

## 3.2 Configuration Management

### 3.2.1 Description and Priority
Configuration Management is essential for customizing and controlling the system settings via API. It has a high priority due to its role in tailoring the system to specific operational needs.

### 3.2.2 Functional Requirements
- FR2.1: Should accept JSON payloads for configuration changes.
- FR2.2: Must be able to parse and execute configuration commands received via API.
- FR2.3: Should log all configuration changes and responses for audit and troubleshooting purposes.

## 3.3 Database Interactions

### 3.3.1 Description and Priority
Database Interactions enable the system to execute SQL commands for data management. This feature has a medium priority and provides essential functionality for data storage and manipulation.

### 3.3.2 Functional Requirements
- FR3.1: Must interface with SQL-compatible databases to execute provided queries.
- FR3.2: Should provide error handling and logging for all database operations.
- FR3.3: Must ensure data integrity and security during all database interactions.

## 3.4 API Integration

### 3.4.1 Description and Priority
API Integration is a high-priority feature that allows the system to communicate with external systems and services. It is crucial for the extensibility and versatility of MainOp.

### 3.4.2 Functional Requirements
- FR4.1: Must expose RESTful API endpoints for system interaction.
- FR4.2: Should ensure secure access to APIs with authentication and authorization mechanisms.
- FR4.3: Must provide comprehensive API documentation for developers and integrators.

# 4. External Interface Requirements

## 4.1 User Interfaces

### 4.1.1 Graphical User Interface (GUI)
- The system shall provide a GUI for easy monitoring and configuration, especially for users not comfortable with CLI.
- The GUI shall display real-time system status, logs, and configuration options.
- The GUI should be intuitive and user-friendly, catering to non-technical users.

### 4.1.2 Command Line Interface (CLI)
- A CLI shall be available for advanced users, providing detailed control and configuration capabilities.
- The CLI shall support all functionalities available in the GUI.
- The CLI should provide clear and concise feedback for user commands.

## 4.2 Hardware Interfaces
- The Core-Layer shall be hardware agnostic and capable of running on standard computing hardware.
- It shall interface with network hardware for connectivity and data transmission.
- There shall be provisions for interfacing with sensors and IoT devices if required.

## 4.3 Software Interfaces
- The system shall interface with SQL databases like MySQL, PostgreSQL, and Oracle for data storage and retrieval.
- It shall support integration with standard web servers and application servers.
- The system should be compatible with major operating systems including Windows, Linux, and MacOS.

## 4.4 Communications Interfaces
- The system shall use HTTP/HTTPS protocols for API communications.
- It shall support MQTT or other IoT protocols for sensor data communication if required.
- The system should ensure secure and encrypted data transmission.

# 5. Other Nonfunctional Requirements

## 5.1 Performance Requirements
- The Core-Layer should handle API requests with minimal latency, aiming for response times under 100 milliseconds.
- It should be capable of handling high volumes of concurrent requests without degradation in performance.
- The system should optimize resource usage to ensure efficient operation, especially in cloud or virtualized environments.

## 5.2 Safety Requirements
- The system shall include measures to prevent data loss or corruption.
- In the event of a critical failure, the system should revert to a safe state to avoid any hazardous conditions.
- Regular backups and fail-safe mechanisms should be implemented to protect against data and operational losses.

## 5.3 Security Requirements
- The system shall implement industry-standard encryption for data at rest and in transit.
- User authentication and authorization mechanisms must be in place for accessing the system’s functionalities.
- Regular security audits and updates are required to address vulnerabilities and ensure compliance with security standards.

## 5.4 Software Quality Attributes
- **Reliability**: The system should have high uptime and recover gracefully from failures.
- **Usability**: The GUI and API interfaces should be user-friendly and intuitive.
- **Maintainability**: The codebase must be well-documented, modular, and easy to update and maintain.
- **Scalability**: The system should be scalable to accommodate growth in data volume and user count.
- **Interoperability**: The system should integrate seamlessly with other systems and platforms.

# 6. Other Requirements

## 6.1 Compliance
- The system shall comply with relevant international and national standards and regulations concerning software systems, particularly those related to data protection, privacy, and digital security.
- Compliance with industry-specific standards (if applicable) shall also be ensured, depending on the deployment environment of MainOp.

## 6.2 Documentation
- Comprehensive documentation shall be provided, covering all aspects of the system including installation, configuration, usage, and API references.
- The documentation should be clear, concise, and accessible to both technical and non-technical users.
- Regular updates to the documentation are required to reflect any changes or updates in the system.

## 6.3 Training and Support
- Adequate training materials and resources shall be provided to assist users in understanding and operating the system effectively.
- User support, including troubleshooting guides, FAQs, and customer service contact information, shall be readily available.

