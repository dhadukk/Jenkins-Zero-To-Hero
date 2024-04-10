# Use an appropriate base image
FROM ubuntu:20.04

# Install necessary dependencies
RUN apt-get update && \
    apt-get install -y wget && \
    wget https://download.uipath.com/UiPathStudio.msi && \
    apt-get install -y unzip && \
    apt-get clean

# Install UiPath Studio
RUN dpkg -i UiPathStudio.msi

# Set the working directory
WORKDIR /project

# Copy the UiPath project files into the container
COPY . /project

# Create the output directory
RUN mkdir /output

# Build the project using the UiPath CLI
RUN uipath-cli pack /project/project.json --output /output

# Upload the package to Orchestrator using the UiPath CLI
CMD uipath-cli push /output/project.zip --orchestratorurl "https://cloud.uipath.com/untieit2/DefaultTenant/orchestrator_" --folder "kinjal" --tenant "Default" --username "admin@untie-it.com" --password "Admin@321!"

