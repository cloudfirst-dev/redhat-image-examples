FROM registry.access.redhat.com/ubi8/nodejs-12

# Copying in source code
COPY app /opt/app-root/src

# Run build and perform cleanup
# Add extra build steps here if necessary
RUN NODE_ENV=development npm install && \
      npm run build --if-present && \
      npm prune

# Command to start app (DO NOT CHANGE)
CMD /usr/libexec/s2i/run
