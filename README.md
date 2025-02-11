# Qt-QML Application Starter Kit with Hexagonal Architecture

## Overview
This project is a Qt-QML starter kit designed to build scalable and maintainable applications using Hexagonal Architecture principles, while being compatible with the MVC design pattern. It provides a modular and extensible structure that supports plugins for both backend and UI components, modern design themes, and a variety of services for seamless communication and data management. The starter kit is ideal for applications requiring advanced features like remote UI, multi-database support, real-time data streaming, and multiprocessing services.

---

## Features

### Core Features
1. **Hexagonal Architecture**: ⚙️ Decouples the core business logic from external dependencies.
2. **MVC Design Compatibility**: 🖼️ Provides a clear separation of views, controllers, and models.
3. **Plugin Support**: 🔌 Allows seamless addition of backend and UI components.
4. **Modern Design and Themes**: 🎨 Includes customizable design themes and a theming engine.
5. **Custom Components and Types**: 🧩 Easily reusable and extendable components.
6. **Multi-Database Support**:
   - 📊 Time-series database
   - 🗄️ PostgreSQL
7. **QSettings Service**: 🛠️ Manages application configurations and settings.
8. **Communication Services**:
   - **QRemoteObject** for remote object communication. 🌐
   - **MQTT/RabbitMQ/Kafka** for real-time data streaming. 📡
   - **REST API and Socket.IO** for external service bindings and real-time property updates. 🌍
9. **Network Manager**: 🔗 Handles network operations and REST API communication.
10. **Remote UI**: 🖥️ Enables control and interaction with a UI hosted remotely, supporting real-time updates and property bindings.
11. **Multiprocessing Services**: 🧵 Supports background task management and multiprocessing.
12. **Binding Services**: 🪢 Simplifies data binding between QML and backend, supporting remote property synchronization.
13. **Pipeline Processing**: 🛠️ For data processing and transformation workflows.
14. **Task Manager**: 📋 Handles background tasks efficiently.

---

## Advantages of the Design Pattern

1. **Separation of Concerns**: ✂️ The Hexagonal Architecture clearly separates core business logic from external dependencies, making the application easier to maintain and extend.
2. **Modularity**: 🧩 By adhering to a plugin-based structure, components can be added or replaced without impacting the rest of the system.
3. **Testability**: ✅ Decoupled design ensures that core logic can be tested independently of external services or UI.
4. **Scalability**: 📈 The architecture is well-suited for adding features such as multi-database support, streaming data services, or additional plugins.
5. **Flexibility**: 🤹 Enables support for multiple communication protocols (e.g., MQTT, RabbitMQ, Kafka, REST API, Socket.IO) and remote UI capabilities.
6. **Reusability**: 🔄 Custom components and services are reusable across multiple projects or modules.
7. **Future-Proofing**: 🔮 Designed to accommodate new technologies and standards with minimal disruption.
8. **Ease of Maintenance**: 🛠️ Clear structure and separation of responsibilities simplify debugging and updates.
9. **Enhanced User Experience**: 🌟 With a modern design and theme support, applications built on this starter kit offer a polished and professional UI.

---

## File and Folder Structure

```plaintext
project-root/
├── app/
│   ├── core/                   # Core business logic (Hexagonal Architecture)
│   │   ├── domain/             # Domain layer (Entities, Aggregates, DTOs)
│   │   │   ├── entities/       # Core business entities
│   │   │   ├── modules/        # Value objects
│   │   │   ├── dtos/           # Data Transfer Objects (DTOs)
│   │   ├── application/        # Application layer (Use cases, Services)
│   │   │   ├── logics/         # Business logic operations
│   │   │   ├── services/       # Core services (DB, communication, etc.)
│   │   │   ├── events/         # Event-driven architecture
│   │   ├── infrastructure/     # Infrastructure layer (External dependencies)
│   │   │   ├── database/       # Database management (PostgreSQL, Time-series DB)
│   │   │   ├── bindings/       # Messaging brokers , Qt-Qml realtime bindings (RabbitMQ, socketio , ...)
│   │   │   ├── logging/        # Logging and monitoring services
│   │   ├── plugins/            # Plugin system (Backend)
│   │   ├── pipelines/          # Data processing pipelines
│   │   ├── task_manager/       # Background task handling
│   │   ├── configs/            # Configuration files (e.g., QSettings, JSON, YAML)
│   │   ├── utils/              # Utility functions
│   ├── ui/                     # UI Layer (Presentation)
│   │   ├── components/         # Custom reusable UI components
│   │   ├── themes/             # Theming engine and styles
│   │   ├── views/              # QML views
│   │   ├── controllers/        # UI controllers handling logic
│   │   ├── plugins/            # UI plugins for extensions
│   │   ├── templates/          # UI templates for app
│   ├── bindings/               # QML-backend data binding
│   ├── settings/               # Application settings and configuration
│   ├── communication/          # Communication Layer
│   │   ├── services/           # Core communication services
│   │   │   ├── messages/       # Message queue services (RabbitMQ, MQTT)
│   │   │   ├── api_gateway/    # API service handling external communication
│   │   │   ├── datasources/    # External data sources (Remote APIs, QRemoteObject)
│   │   │   ├── events/         # Event-driven service
│   │   │   ├── socket_io/      # WebSocket services
│   │   ├── connectors/         # Low-level network connectors and drivers
│   │   │   ├── mqtt/           # MQTT service
│   │   │   ├── rabbitmq/       # RabbitMQ service
│   │   │   ├── rest/           # REST API connectors
│   │   │   ├── socket/         # Socket.IO low-level handlers
│   │   │   ├── qremote/        # QRemoteObject connectors
│   │   ├── configs/            # Configuration files for communication services
│   └── network/                # Network management
├── common/                     # Common shared resources
│   ├── types/                  # Global type definitions (structs, enums, interfaces)
│   ├── modules/                # Reusable modules across the app
│   ├── properties/             # Shared class properties and constants
├── tests/                      # Unit and integration tests
├── docs/                       # Documentation
├── scripts/                    # Helper scripts
├── CMakeLists.txt              # Build configuration
└── README.md                   # Project description and setup instructions

```

---

## Getting Started

### Prerequisites
1. **Qt Framework**: 🛠️ Version 6.5 or higher.
2. **CMake**: 🏗️ For build configuration.
3. **Supported Databases**: 🗄️ PostgreSQL, InfluxDB (for time-series data).
4. **Messaging Brokers**: 📡 MQTT, RabbitMQ, Kafka.

### Setup
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. Configure the project:
   ```bash
   cmake -B build -S .
   ```

3. Build the project:
   ```bash
   cmake --build build
   ```

4. Run the application:
   ```bash
   ./build/app
   ```

---

## Plugin Development

### Adding a Backend Plugin
1. 📂 Create a new folder under `app/core/plugins/`.
2. ✏️ Implement your plugin logic by inheriting from the base plugin interface.
3. 🛠️ Register your plugin in the core plugin manager.

### Adding a UI Plugin
1. 📂 Create a new folder under `app/ui/plugins/`.
2. 🖼️ Add custom QML components or views as needed.
3. 🛠️ Register your plugin in the UI plugin manager.

---

## Key Services and Modules

### QSettings Service
Manages application settings with persistence.
- **Location**: `app/settings/`
- **Usage**:
  ```cpp
  QSettings settings;
  settings.setValue("theme", "dark");
  QString theme = settings.value("theme", "light").toString();
  ```

### Communication Services
- **MQTT Service**: 📡 For real-time messaging.
- **RabbitMQ**: 📬 For message queues.
- **Kafka**: 🚀 For streaming data pipelines.
- **REST API and Socket.IO**: 🌍 For external service connectivity and real-time property updates.

### Background Task Manager
- **Location**: `app/core/task_manager/`
- **Usage**: 📋 Create and manage background tasks with multiprocessing capabilities.

---

## Advanced Features

### Modern Design and Themes
- 🎨 Located in `app/ui/themes/`.
- Provides light and dark themes with support for custom theming.

### Multi-Database Support
- 🗄️ Integrates with PostgreSQL and time-series databases.
- Configuration files located in `app/core/services/`.

### Remote UI
- 🖥️ Enables remote interaction via QRemoteObject.
- 🌍 Supports external connectivity through REST APIs and Socket.IO for seamless property binding and updates.

---

## Roadmap

1. **Phase 1**: 🛠️ Core Architecture
   - Implement Hexagonal Architecture base.
   - Create initial DTOs, services, and controllers.

2. **Phase 2**: 🎨 UI and Theme Engine
   - Build reusable components and views.
   - Add theme support.

3. **Phase 3**: 🌐 Communication Services
   - Integrate QRemoteObject, MQTT, RabbitMQ, Kafka, REST API, and Socket.IO.

4. **Phase 4**: 🔌 Plugin System
   - Develop a plugin manager for backend and UI.
   - Add sample plugins.

5. **Phase 5**: ⚙️ Advanced Features
   - Add background task management.
   - Support multi-database connections.

---

## Contribution Guidelines
1. 🍴 Fork the repository and create a new branch for your feature.
2. 📝 Follow the project’s coding guidelines.
3. 📤 Submit a pull request with a detailed description.

---

## License
This project is licensed under the MIT License. See `LICENSE` for more details.

---

## Contact
For questions or support, feel free to contact the project maintainer at [amirtaherkhani@outlook.com], [masiha98@yahoo.com] .

