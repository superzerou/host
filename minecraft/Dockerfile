FROM openjdk:17-jdk-slim

WORKDIR /paper

# Install required tools
RUN apt-get update && apt-get install -y curl

# Set environment variables
ENV PAPER_VERSION=1.21.5 \
    PAPER_BUILD=latest \
    MEMORY=2G \
    EULA=true

# Download Paper jar
RUN curl -o paper.jar https://api.papermc.io/v2/projects/paper/versions/${PAPER_VERSION}/builds/${PAPER_BUILD}/downloads/paper-${PAPER_VERSION}-${PAPER_BUILD}.jar

EXPOSE 25565

CMD java -Xms$MEMORY -Xmx$MEMORY -jar paper.jar nogui
