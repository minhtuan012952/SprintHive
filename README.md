Front-End (Vue.js)

Switch to Vue 3 + Vite (optional, but modern).

Adopt Tailwind CSS for styling.

Use dark/light themes with smooth transitions.

Replace bootstrap-style components with customized dashboard UI (rounded cards, shadows, gradients).

Back-End (Spring Boot)

Keep structure, but rename packages:

com.taskagile → com.sprinthive


Update properties:

spring.datasource.url=jdbc:mysql://localhost:3306/sprinthive?useSSL=false


Rename the JAR artifact:

app-0.0.1-SNAPSHOT.jar → sprinthive-0.0.1.jar

Docker / Branding

Update Dockerfile and commands:

$ mvn clean package
$ cp target/sprinthive-0.0.1.jar docker/app.jar
$ docker build -t sprinthive:dev docker/
$ docker run --rm --name sprinthive -e "SPRING_PROFILES_ACTIVE=dev" -p 8080:8080 -p 9000:9000 sprinthive

Logo / Theme

Colors: 🟢 #00C896 + dark gray background (#1F2937)

Typography: Inter / Poppins

Iconography: Feather or Lucide

🧱 3. Folder / Code Name Changes

If you want a scriptable rename (Linux/Mac example):

find . -type f -exec sed -i 's/taskagile/sprinthive/g' {} +
find . -type f -exec sed -i 's/TaskAgile/SprintHive/g' {} +
mv src/main/resources/taskagile src/main/resources/sprinthive

💡 Final Overview

Old Project: TaskAgile
New Project: SprintHive
Tech Stack: Vue.js 2 → optionally Vue 3 + Vite, Spring Boot 2, MySQL, RabbitMQ
Style: Tailwind-based, clean dashboard, light/dark theme
Docker Image: sprinthive:dev
Port: 8080 backend / 9000 frontend
