# Use the official UiPath base image
FROM uipathplatform/automation:21.10

# Copy your UiPath project files into the container
COPY . /project

# Set the working directory to your project directory
WORKDIR /project

# Create the output directory
RUN mkdir /output

# Build the project using the UiPath CLI
RUN uipath-cli pack /project/project.json --output /output

# Upload the package to Orchestrator using the UiPath CLI
CMD uipath-cli push /output/project.zip --orchestratorurl "https://cloud.uipath.com/untieit2/DefaultTenant/orchestrator_" --folder "kinjal" --tenant "Default" --username "admin@untie-it.com" --password "Admin@321!"

