# Use official Tomcat 10 base image
FROM tomcat:10-jdk17

# Remove default Tomcat applications
RUN rm -rf /usr/local/tomcat/webapps/*

# Copy WAR file from build context to webapps directory
COPY ROOT.war /usr/local/tomcat/webapps/ROOT.war

# Set environment variables
ENV CATALINA_OPTS="-Xms512m -Xmx1024m -XX:+UseParallelGC"

# Expose default Tomcat port
EXPOSE 8080

# Start Tomcat
CMD ["catalina.sh", "run"]

